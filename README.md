# Git Flow en un Proyecto PHP

## 1. Creación del repositorio y configuración inicial

### Pasos realizados:

1. **Creación del repositorio:** Se creó un repositorio en GitHub con el nombre `gitflow-php-Eduardo`.
2. **Clonación del repositorio:**
   ```sh
   git clone https://github.com/EduRosa96/gitflow-php-Eduardo.git
   cd gitflow-php-Eduardo
   ```
3. **Inicialización de Git Flow:**
   ```sh
   git flow init
   ```
   - Se seleccionó `main` como rama principal.
   - Se creó `develop` como rama de desarrollo.

### Entregables:

- **URL del repositorio:** [GitHub - gitflow-php-Eduardo](https://github.com/EduRosa96/gitflow-php-Eduardo)
- **Captura del historial de ramas:**
  ```sh
  git branch -a
  ```
- **Este README.md con los pasos documentados.**

---

## 2. Creación de un archivo PHP

### Pasos realizados:

1. **Creación de una nueva funcionalidad en Git Flow:**
   ```sh
   git flow feature start crear-mi-archivo
   ```
2. **Creación del archivo ****`alumnos/Eduardo.php`****:**
   ```sh
   mkdir -p alumnos
   echo '<?php
   // Archivo: alumnos/Eduardo.php
   echo "Hola, soy Eduardo y estoy aprendiendo Git Flow!";
   ?>' > alumnos/Eduardo.php
   ```
3. **Confirmación y subida de cambios:**
   ```sh
   git add alumnos/Eduardo.php
   git commit -m "Añadido archivo Eduardo.php en alumnos/"
   git push -u origin feature/crear-mi-archivo
   ```
4. **Finalización de la funcionalidad y fusión en ****`develop`****:**
   ```sh
   git flow feature finish crear-mi-archivo
   git push origin develop
   ```

### Entregables:

- **Captura del log de commits:**
  ```sh
  git log --oneline --graph
  ```
- **Este README.md con la documentación.**

---

## 3. Modificación de un archivo existente

### Pasos realizados:

1. **Creación de una nueva funcionalidad:**
   ```sh
   git flow feature start modificar-index
   ```
2. **Modificación de ****`index.php`**** para incluir ****`alumnos/Eduardo.php`****:**
   ```php
   <?php
   include "alumnos/Eduardo.php";
   ?>
   ```
3. **Confirmación y subida de cambios:**
   ```sh
   git diff  # Captura del diff antes de confirmar
   git add index.php
   git commit -m "Incluido Eduardo.php en index.php"
   git push -u origin feature/modificar-index
   ```
4. **Finalización de la funcionalidad y fusión en ****`develop`****:**
   ```sh
   git flow feature finish modificar-index
   git push origin develop
   ```

### Entregables:

- **Captura de ****`git diff`**** antes de confirmar.**
- **Este README.md con los pasos documentados.**

---

## 4. Resolución de conflictos

### Pasos realizados:

1. **Modificación de ****`index.php`**** simultáneamente con un compañero.**
2. **Intento de fusión en ****`develop`****, generando un conflicto:**
   ```sh
   git merge feature/modificar-index
   ```
3. **Resolución del conflicto manualmente editando ****`index.php`****.**
4. **Confirmación de los cambios:**
   ```sh
   git add index.php
   git commit -m "Resuelto conflicto en index.php"
   git push origin develop
   ```

### Entregables:

- **Captura de ****`git status`**** mostrando el conflicto.**
- **Captura del archivo ****`index.php`**** después de la resolución.**
- **Explicación en este README.md.**

---

## 5. Eliminación de un archivo

### Pasos realizados:

1. **Creación de la funcionalidad:**
   ```sh
   git flow feature start borrar-mi-archivo
   ```
2. **Eliminación del archivo ****`alumnos/Eduardo.php`****:**
   ```sh
   rm alumnos/Eduardo.php
   ```
3. **Confirmación y subida de cambios:**
   ```sh
   git add alumnos/Eduardo.php
   git commit -m "Eliminado Eduardo.php"
   git push -u origin feature/borrar-mi-archivo
   ```
4. **Finalización de la funcionalidad:**
   ```sh
   git flow feature finish borrar-mi-archivo
   git push origin develop
   ```

### Entregables:

- **Captura del log (****`git log --oneline`****).**
- **Este README.md con la documentación.**

---

## 6. Publicación de la versión final

### Pasos realizados\:git

1. **Creación de una release en Git Flow:**
   ```sh
   git flow release start v1.0
   ```
2. **Finalización de la release y fusión en ****`main`****:**
   ```sh
   git flow release finish v1.0
   ```
3. **Creación de una etiqueta (tag) ****`v1.0`****:**
   ```sh
   git tag -a v1.0 -m "Versión 1.0 estable"
   git push origin v1.0
   ```

### Entregables:

- **Comandos utilizados en la publicación de la versión.**
- **Este README.md con la documentación detallada.**

