# Página FAB LAB UPC — Monterrico

Home page interactiva del FAB LAB con robot 3D (modelo Tripo integrado con Three.js).

## Estructura

```
pagina-fablab-upc/
├── index.html                  → home (robot 3D + menú; todo autocontenido, funciona sin internet)
├── simuladores/
│   ├── corte-laser.html        → PENDIENTE: reemplazar con el simulador real
│   └── cnc-shopbot.html        → PENDIENTE: reemplazar con el simulador real
└── README.md
```

## Funcionamiento

- El robot sigue al cursor; al hacer click en una opción el ojo destella en turquesa.
- **Simuladores** ramifica en Corte láser y CNC ShopBot; al elegir uno navega a `simuladores/<nombre>.html`.
- Cronograma, Anuncios y Contacto aún no tienen página destino (buscar `AQUI va la navegacion real` en index.html para cablearlas).

## Cómo subirlo a GitHub

1. Crear cuenta/entrar en github.com → botón **New repository** → nombre: `pagina-fablab-upc` → Public → Create.
2. Click en **"uploading an existing file"** → arrastrar TODO el contenido de esta carpeta (index.html, README.md, carpeta simuladores) → **Commit changes**.

## Cómo publicarlo en Vercel

1. Entrar a vercel.com → **Sign up → Continue with GitHub**.
2. **Add New → Project** → Import del repo `pagina-fablab-upc`.
3. Framework Preset: **Other** (sin build, es sitio estático) → **Deploy**.
4. URL pública resultante: `pagina-fablab-upc.vercel.app`.

Cada commit en GitHub redespliega automáticamente en Vercel.

Alternativa sin Vercel: GitHub Pages (Settings → Pages → Source: `main`) →
`https://<tu-usuario>.github.io/pagina-fablab-upc/`.

Para ediciones futuras: editar desde github.com (ícono lápiz) o clonar con GitHub Desktop.

## Notas técnicas

- Modelo 3D: GLB optimizado (1M → 63k vértices, textura 8K → 1K JPEG). Original en Tripo.
- La textura viaja aparte del GLB (data URI) por compatibilidad con visores restrictivos.
- Motor: Three.js r160 empaquetado dentro del index.html (sin CDN).
- Ajustes de seguimiento del cursor: constantes `SIGN_X, SIGN_Y, GAIN_H, GAIN_V` dentro del script.

---
Creado: 2026-07-05 · Proyecto de Jose (FAB LAB UPC Monterrico)
