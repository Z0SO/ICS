
### **Ejemplo 1: Usando Sourcetree**
#### Objetivo: Practicar cómo hacer un *rebase* en una rama y resolver conflictos.
- [ ] Completado.


#### **Parte 1: Rebasing de una rama llamada `feature1`**

1. **Crea un repositorio local llamado `projectg`:**
   - Abre Sourcetree.
   - Haz clic en "Archivo > Nuevo > Crear Repositorio Local".
   - Nómbralo `projectg`.

2. **Crea un commit inicial:**
   - Agrega un archivo vacío llamado `fileA.txt` al repositorio.
   - Haz un commit con el mensaje: `add fileA.txt`.

3. **Crea una rama `feature1`:**
   - En Sourcetree, crea una nueva rama llamada `feature1`.

4. **Haz un commit en la rama `feature1`:**
   - Abre `fileA.txt` y escribe `feature 1 wip`.
   - Haz un commit con el mensaje: `add feature 1 wip`.

5. **Regresa a la rama `master`:**
   - Cambia a la rama `master` en Sourcetree.
   - Agrega un archivo vacío `fileB.txt` y haz un commit con el mensaje: `add fileB.txt`.

6. **Mira el gráfico de commits:**
   - En Sourcetree, abre el gráfico de commits. Verás que ya no es lineal porque hay dos ramas separadas (`master` y `feature1`).

7. **Haz un rebase de `feature1` sobre `master`:**
   - Cambia a la rama `feature1`.
   - Haz clic derecho sobre el último commit de `master` y selecciona "Rebase...".
   - Confirma el rebase haciendo clic en "OK".

8. **Verifica el gráfico de commits:**
   - Ahora el historial debe ser lineal.
   - En la rama `feature1`, verifica que el archivo `fileB.txt` está presente.



#### **Parte 2: Rebasing y resolución de un conflicto**

1. **Regresa a la rama `master`:**
   - Cambia a la rama `master`.

2. **Haz un commit en `master`:**
   - Abre `fileA.txt` y escribe `feature 2`.
   - Haz un commit con el mensaje: `add feature 2`.

3. **Haz un rebase de `feature1` sobre `master`:**
   - Cambia a la rama `feature1`.
   - Haz clic derecho en el último commit de la rama `master` y selecciona "Rebase...".
   - Confirma el rebase.

4. **Resuelve el conflicto:**
   - Sourcetree mostrará un mensaje diciendo que hay un conflicto en `fileA.txt`.
   - Abre `fileA.txt` y combina los cambios para que quede así:
     ```
     feature 1 wip
     feature 2
     ```
   - Guarda el archivo.

5. **Continúa el rebase:**
   - Haz clic derecho en el último commit de `feature1` y selecciona "Rebase...".
   - Selecciona "Continuar Rebase".

6. **Verifica el gráfico de commits:**
   - Ahora el gráfico debe ser lineal nuevamente.

7. **Elimina el repositorio:**
   - Si ya no necesitas el repositorio `projectg`, puedes eliminarlo desde tu sistema.

---

### **Ejemplo 2: Usando la línea de comandos**
#### Objetivo: Hacer lo mismo que en Sourcetree, pero usando comandos de Git.
- [ ] Completado.

#### **Parte 1: Rebasing de una rama llamada `feature1`**

1. **Crea un repositorio local llamado `projectg`:**
   ```bash
   mkdir projectg
   cd projectg
   git init
   ```

2. **Crea un commit inicial:**
   ```bash
   touch fileA.txt
   git add fileA.txt
   git commit -m "add fileA.txt"
   ```

3. **Crea una rama `feature1`:**
   ```bash
   git checkout -b feature1
   ```

4. **Haz un commit en la rama `feature1`:**
   ```bash
   echo "feature 1 wip" > fileA.txt
   git add fileA.txt
   git commit -m "add feature 1 wip"
   ```

5. **Regresa a la rama `master`:**
   ```bash
   git checkout master
   touch fileB.txt
   git add fileB.txt
   git commit -m "add fileB.txt"
   ```

6. **Verifica el gráfico de commits:**
   ```bash
   git log --oneline --graph --all
   ```
   Verás que el historial no es lineal.

7. **Haz un rebase de `feature1` sobre `master`:**
   ```bash
   git checkout feature1
   git rebase master
   ```

8. **Verifica el gráfico de commits:**
   ```bash
   git log --oneline --graph --all
   ```
   Ahora el historial debe ser lineal.


#### **Parte 2: Rebasing y resolución de un conflicto**

1. **Regresa a la rama `master`:**
   ```bash
   git checkout master
   ```

2. **Haz un commit en `master`:**
   ```bash
   echo "feature 2" >> fileA.txt
   git add fileA.txt
   git commit -m "add feature 2"
   ```

3. **Haz un rebase de `feature1` sobre `master`:**
   ```bash
   git checkout feature1
   git rebase master
   ```

4. **Resuelve el conflicto:**
   - Git te dirá que hay un conflicto en `fileA.txt`.
   - Abre `fileA.txt` y edítalo para que quede así:
     ```
     feature 1 wip
     feature 2
     ```
   - Guarda los cambios.

5. **Continúa el rebase:**
   ```bash
   git add fileA.txt
   git rebase --continue
   ```

6. **Verifica el gráfico de commits:**
   ```bash
   git log --oneline --graph --all
   ```
   El gráfico debe ser lineal nuevamente.

7. **Elimina el repositorio:**
   Si ya no necesitas el repositorio:
   ```bash
   cd ..
   rm -rf projectg
   ```

