# 🌿 Flujo de Trabajo Git — La Isla del Tesoro

---

## Ramas principales

### `main`
- Rama de producción estable
- Solo recibe merges desde `develop` cuando hay una versión lista
- **Nadie hace commits directos aquí**

### `develop`
- Rama de desarrollo activo
- Aquí se integran todas las funcionalidades terminadas
- Es la rama base para crear ramas `feature/*`

---

## Ramas de funcionalidad

### `feature/*`
Se crean desde `develop` para trabajar en una funcionalidad específica.

**Cómo crear una rama feature:**
```bash
git checkout develop
git pull origin develop
git checkout -b feature/nombre-de-la-funcionalidad
```

**Ejemplos de ramas feature:**
- `feature/movimiento-jugador`
- `feature/sistema-armas`
- `feature/diseno-nivel-1`
- `feature/menu-principal`

---

## Flujo de trabajo paso a paso

```bash
# 1. Actualizar develop
git checkout develop
git pull origin develop

# 2. Crear tu rama feature
git checkout -b feature/mi-funcionalidad

# 3. Trabajar y hacer commits
git add .
git commit -m "feat: descripción clara del cambio"

# 4. Subir tu rama
git push origin feature/mi-funcionalidad

# 5. Hacer merge a develop (o abrir Pull Request)
git checkout develop
git merge feature/mi-funcionalidad
git push origin develop
```

---

## Convención de commits

| Prefijo | Uso |
|---------|-----|
| `feat:` | Nueva funcionalidad |
| `fix:` | Corrección de bug |
| `docs:` | Cambios en documentación |
| `art:` | Recursos gráficos o de audio |
| `refactor:` | Mejora de código sin cambiar funcionalidad |

**Ejemplo:**
```
feat: agregar movimiento lateral del jugador
fix: corregir colisión con plataformas
docs: actualizar README con instrucciones de Unity
```

---

## Estructura de ramas actual

```
main
└── develop
    ├── feature/estructura-inicial ✅ (mergeada)
    ├── feature/movimiento-jugador (próxima)
    └── feature/diseno-nivel-1 (próxima)
```
