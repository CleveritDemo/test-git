# Guía de Comandos Git - Subir Proyecto a Main desde Cero

## 1. Preparación inicial
```bash
# Navegar a la carpeta del proyecto
cd mi-proyecto

# Inicializar repositorio Git
git init

# Configurar usuario y email
git config user.name "tu-usuario"
git config user.email "tu-email@ejemplo.com"
```

## 2. Conectar con GitHub
```bash
# Agregar repositorio remoto
git remote add origin https://github.com/usuario/repositorio.git
```

## 3. Subir código por primera vez
```bash
# Agregar todos los archivos
git add .

# Hacer commit inicial
git commit -m "Commit inicial"

# Crear y cambiar a rama main (si no existe)
git checkout -b main

# Subir a GitHub
git push -u origin main
```

## 4. Flujo normal para cambios posteriores
```bash
# 1. Agregar cambios
git add .

# 2. Hacer commit
git commit -m "Descripción del cambio"

# 3. Traer cambios remotos (IMPORTANTE: hacerlo ANTES del push)
git pull origin main

# 4. Subir cambios
git push origin main
```

## 5. Comandos útiles adicionales
```bash
# Ver estado del repositorio
git status

# Ver ramas disponibles
git branch

# Ver repositorios remotos configurados
git remote -v

# Eliminar rama local
git branch -d nombre-rama

# Eliminar rama remota
git push origin --delete nombre-rama

# Cambiar mensaje del último commit
git commit --amend -m "Nuevo mensaje"

# Limpiar credenciales almacenadas (Windows)
cmdkey /delete:git:https://github.com
```

## 6. Solución de problemas comunes

### Error de permisos (403)
- Verificar que estás autenticado con la cuenta correcta
- Limpiar credenciales: `cmdkey /delete:git:https://github.com`
- Configurar usuario correcto: `git config user.name "tu-usuario"`

### Error "refusing to merge unrelated histories"
```bash
git pull origin main --allow-unrelated-histories
```

### Error "src refspec main does not match any"
- Verificar en qué rama estás: `git branch`
- Usar la rama correcta en el push: `git push origin nombre-rama-actual`

## 7. Conceptos importantes

**¿Qué es origin?**
- Es el nombre del repositorio remoto (GitHub)
- Se configura automáticamente al clonar o manualmente con `git remote add`

**¿Cuándo usar pull?**
- Siempre ANTES de hacer push
- Al iniciar el día de trabajo
- Cuando trabajas en equipo

**¿Qué son los cambios remotos?**
- Modificaciones que están en GitHub pero no en tu computadora local
- Pueden ser de otros desarrolladores o tus propios cambios desde otra máquina

---
*Guía creada: Septiembre 18, 2025*