# Estado del trabajo — pausa 15 ago 2026

Todo commiteado (`e88d36f`) y desplegado al dev theme. Árbol limpio.

**Preview:** https://feelgoodpharma-8716.myshopify.com?preview_theme_id=188610969921
**Dev theme:** `188610969921` · **FGP 2.0** (`187380990273`) reemplazará al live

---

## ⏸️ Lo que quedó a medio camino

**Imagen custom para tarjetas de producto** — el último cambio.

`snippets/card-product.liquid` ahora prefiere el metafield `custom.card_image`
y usa la imagen destacada como fallback. **El código está listo y desplegado,
pero el metafield todavía no existe**, así que no se ve ningún cambio aún.

Para activarlo:

1. Admin → Settings → **Custom data** → **Products** → Add definition
2. Name: `Card image` · Namespace and key: **`custom.card_image`** · Type: **File → Image**
3. Products → Synbiotic+ → llenar ese campo con una foto lifestyle

Con eso, la tarjeta de "También te puede gustar" usa la foto atractiva y la
página de producto conserva el packshot.

**Contexto:** el frasco de Synbiotic+ se ve cortado en las tarjetas porque la
imagen destacada **ya viene recortada en el archivo original** — no es un
problema de CSS. Por eso el metafield es la salida correcta.

---

## ✅ Terminado

- **Traducciones ES/EN** — 99 claves `fgp.*`, plantillas 100 % en español (231
  strings), `translations-en.csv` con 504 filas listo para importar
- **Voseo** — 18 strings + 8 en `locales/es.json`
- **Página de contacto** — iconos SVG, WhatsApp con mensaje predefinido,
  formulario corregido, horarios alineados con el footer
- **Logos** — blanco en el header, azul en el login (estaban invertidos)
- **Imágenes de producto** — sin recortes ni bandas blancas
- **Tarjetas** — alineadas al Figma (vendor visible, botón cyber grape,
  precio y botón en la misma fila)
- **Bugs corregidos:** `hero-split` tenía JSON inválido y no cargaba;
  español hardcodeado en el login; `general.meta.*` faltaba en los locales

Docs: `TRANSLATIONS.md` · `POLITICAS.md` (4 políticas redactadas, con
`[CORCHETES]` donde faltan datos)

---

## 🔴 Bloqueantes para lanzar

1. **10 testimonios médicos falsos** — `Dr. Nombre Apellido` en home, Kids,
   Stressbiotic y Synbiotic, con recomendaciones clínicas atribuidas a médicos
   que no existen. Es lo más serio del sitio. Solo hay 2 reales (Dra. Nancy
   Conejo, Doctora Von Saalfeld).
2. **14 reseñas sin verificar** — si son inventadas, aplica lo mismo.
3. ~~Sin analítica~~ — **GA4 sí está activo**: app Google & YouTube instalada
   (mar 2025), pixel *Connected*, Store analytics recibiendo datos. Lo reporté
   mal: busqué scripts en el tema, pero las apps se inyectan vía
   `content_for_header` y no son visibles desde el repo.
   **Falta confirmar Meta Pixel** (Apps → Facebook & Instagram, o
   Settings → Customer events).

## 🟡 Pendientes

- `share_image` vacío → al compartir en WhatsApp no sale imagen
- Placeholders: `Nombre del producto`, `Texto del botón`
- Políticas: pegar `POLITICAS.md` en Settings → Policies y completar corchetes
- Home dice "envío a EE. UU." pero no hay política de envíos internacionales
- Verificar que la página de contacto tenga asignada la plantilla `contact`
- **Inglés (fase 2):** importar `translations-en.csv` — requiere FGP 2.0
  publicado, porque Shopify solo expone secciones del tema publicado
- Kit menciona Stressbiotic (on hold) en 4 lugares de `product.kit.json`
- Tabla comparativa de Stressbiotic: `Upto-proliferating` y
  `Only strains to sleep` sin sentido, más 3 bugs de lógica

---

## ⚠️ Al retomar

**Nunca `theme pull` sin commitear antes.** Ya sobrescribió trabajo una vez.
El repo es la fuente de verdad; usar `theme push`.

Si editás en el **theme editor**, `settings_data.json` y los `templates/*.json`
cambian en el servidor y hay que hacer `pull` para no perder eso. Avisar antes
para sincronizar en el orden correcto.

```
shopify theme push --theme 188610969921
```
