# Balance

Aplicación de presupuesto personal en HTML, CSS y JavaScript. Planificación por meses, movimientos reales, ahorro, inversión y exportaciones para Notion.

## Publicación en GitHub Pages

Repositorio: https://github.com/TheABA15/Balance

1. Sube a la raíz del repositorio los archivos de esta carpeta: `index.html`, `styles.css`, `app.js`, `.nojekyll`, `.gitignore` y `README.md`. No subas el ZIP sin descomprimir ni la carpeta contenedora.
2. En **Settings → Pages → Build and deployment**, selecciona **Deploy from a branch**.
3. Selecciona la rama que contiene los archivos (normalmente `main`) y la carpeta **/ (root)**. Pulsa **Save**.
4. Consulta el despliegue en **Actions**. Cuando termine, GitHub mostrará la dirección de Pages. La dirección esperada para este repositorio es https://theaba15.github.io/Balance/.

Si tu plan de GitHub requiere un repositorio público para Pages, revisa su visibilidad. La web publicada no incluye el acceso privado con ChatGPT del alojamiento anterior.

## Migrar tus datos

Antes de cambiar de dirección, abre la web anterior y selecciona **Exportar copia JSON**. En GitHub Pages, pulsa **Importar copia** y selecciona ese archivo. La importación sustituye los datos del navegador en la nueva dirección.

No subas copias JSON personales ni informes financieros al repositorio. La aplicación empieza vacía: los ejemplos se generan en el navegador cuando los solicitas.

## Funcionamiento

- **Presupuesto:** introduce ingresos previstos y asigna gastos, ahorro e inversión. Puedes añadir categorías y copiar el plan del mes anterior.
- **Movimientos:** registra, edita, busca y elimina movimientos reales.
- **Vista general:** compara lo previsto con lo realizado.
- **Evolución:** compara los últimos seis meses.
- **Exportar a Notion:** descarga un Markdown mensual; en Notion, Importar → Texto y Markdown. Es una copia estática.
- **Copia JSON:** guarda todos los meses y categorías para restaurarlos o trasladarlos.

El disponible es ingresos menos gastos y aportaciones del mes. No representa el saldo bancario ni acumula meses anteriores. Las inversiones reflejan aportaciones, sin rentabilidad o valoración de cartera.

## Arquitectura

Sin backend, base de datos remota, framework ni proceso de compilación. `app.js` mantiene el estado y lo serializa como JSON en `localStorage`, con la clave `balance.personal.v1`. Los datos dependen del origen de la web y del perfil del navegador; no se sincronizan entre dispositivos. Borrar el almacenamiento del sitio elimina los datos locales.

`index.html` contiene la estructura, `styles.css` el diseño responsive y `app.js` los cálculos, validación, persistencia y exportaciones. Las rutas de los recursos son relativas para funcionar bajo `/Balance/`. Google Fonts es opcional: hay fuentes del sistema como alternativa.

## Ejecución local

Desde esta carpeta:

```sh
python -m http.server 8765
```

Abre http://localhost:8765. Este origen tendrá su propio almacenamiento, independiente de GitHub Pages.

## Actualizaciones

Sube los cambios a la rama configurada para Pages. GitHub volverá a publicar el sitio. Mantener el mismo dominio, protocolo y puerto permite conservar el almacenamiento local; no incluyas datos personales en los archivos publicados.
