
# Funciones Más Importantes de Git para Usar con GitHub

## 1. Configuración Inicial
- `git config --global user.name "Tu Nombre"`  
  Configura tu nombre para los commits.
- `git config --global user.email "tuemail@example.com"`  
  Configura tu correo electrónico para los commits.

---

## 2. Manejo de Repositorios
- **Clonar un repositorio**  
  ```bash
  git clone URL_DEL_REPOSITORIO
  ```  
  Descarga una copia del repositorio remoto en tu máquina local.

- **Inicializar un repositorio local**  
  ```bash
  git init
  ```  
  Convierte una carpeta en un repositorio de Git.

---

## 3. Verificar el Estado
- `git status`  
  Muestra el estado de los archivos: cambios realizados, cambios pendientes de confirmación y archivos no rastreados.

---

## 4. Agregar Cambios
- **Agregar archivos al área de preparación (staging area)**  
  ```bash
  git add archivo.txt
  git add .
  ```  
  El primer comando agrega un archivo específico; el segundo, todos los cambios.

---

## 5. Confirmar Cambios (Commits)
- `git commit -m "Mensaje descriptivo del cambio"`  
  Guarda los cambios en el historial de Git.

---

## 6. Sincronización con GitHub
- **Agregar un repositorio remoto**  
  ```bash
  git remote add origin URL_DEL_REPOSITORIO
  ```
  Enlaza el repositorio local con uno remoto en GitHub.

- **Subir cambios al repositorio remoto**  
  ```bash
  git push origin rama
  ```  
  Envía los commits locales a la rama especificada en GitHub.

- **Actualizar la copia local desde el remoto**  
  ```bash
  git pull origin rama
  ```  
  Combina los cambios remotos con tu copia local.

---

## 7. Trabajo con Ramas
- **Crear una nueva rama**  
  ```bash
  git branch nombre_rama
  ```
- **Cambiar de rama**  
  ```bash
  git checkout nombre_rama
  ```
- **Crear y cambiar a una rama nueva al mismo tiempo**  
  ```bash
  git checkout -b nombre_rama
  ```
- **Combinar una rama con otra**  
  ```bash
  git merge nombre_rama
  ```

---

## 8. Manejo de Historial
- **Ver historial de commits**  
  ```bash
  git log
  ```
- **Ver diferencias entre commits**  
  ```bash
  git diff
  ```

---

## 9. Resolver Conflictos
- Git marca los archivos en conflicto para que los resuelvas manualmente.  
  Luego, confirmas los cambios:
  ```bash
  git add archivo_resuelto
  git commit -m "Resuelto conflicto"
  ```

---

## 10. Deshacer Cambios
- **Descartar cambios no confirmados**  
  ```bash
  git checkout archivo.txt
  ```
- **Eliminar un archivo del área de preparación**  
  ```bash
  git reset archivo.txt
  ```

---

## 11. Uso de Tags (Opcional)
- **Crear un tag para marcar un punto específico**  
  ```bash
  git tag -a v1.0 -m "Primera versión"
  ```
- **Subir tags al remoto**  
  ```bash
  git push origin --tags
  ```

---
