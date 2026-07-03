# Portal Premium · Préstamos Flash

Esta carpeta contiene una página estática lista para GitHub Pages.
La página permite que cada cliente consulte su estado con:

- DNI / CUIT
- Código portal

El diseño incluye semáforo automático:

- Verde: al día o cancelado
- Amarillo: vence hoy o vence mañana
- Rojo: hay cuota vencida impaga

## Archivos incluidos

- `index.html`: página principal del portal.
- `styles.css`: diseño premium turquesa.
- `app.js`: lógica de consulta, cuotas y semáforo.
- `config.js`: configuración rápida de marca, moneda y WhatsApp.
- `portal-clientes.json`: archivo de datos. Trae datos DEMO. Hay que reemplazarlo por el que exporta la app.
- `assets/`: ícono y favicon.
- `robots.txt`: intenta evitar indexación en buscadores. No es seguridad real.

## Cómo probar el demo

Abrí el portal ya subido a GitHub Pages e ingresá:

- DNI: `00000000`
- Código: `1234`

## Cómo subirlo a GitHub Pages

1. Crear un repositorio nuevo en GitHub. Ejemplo: `mira-tu-estado-premium`.
2. Subir todos los archivos de esta carpeta a la raíz del repositorio.
3. Entrar a **Settings → Pages**.
4. En **Build and deployment**, elegir:
   - Source: `Deploy from a branch`
   - Branch: `main`
   - Folder: `/root`
5. Guardar.
6. Esperar 1 o 2 minutos hasta que GitHub muestre el link público.

## Cómo actualizar cuotas pagas

Cada vez que registres pagos en la app:

1. Abrí Préstamos Flash.
2. Usá el botón **Exportar portal**.
3. Buscá el archivo generado por la app:
   - `panel_cliente/portal-clientes.json`
4. En GitHub, entrá al repositorio del portal.
5. Reemplazá el archivo `portal-clientes.json` por el nuevo.
6. Hacé **Commit changes**.
7. Esperá 1 o 2 minutos y el portal queda actualizado.

## Muy importante: privacidad

No subas `data.json` completo a GitHub.
Ese archivo puede contener usuarios internos, contraseñas, historial, teléfonos, direcciones y otros datos privados.

Subí solamente `portal-clientes.json`, porque es el archivo pensado para el portal.
Aun así, GitHub Pages es una página estática: el archivo JSON queda publicado. El formulario oculta la información en pantalla, pero no equivale a un login bancario real con servidor privado.

Recomendación: el JSON público debería tener solo lo indispensable:

- DNI / CUIT
- Código portal
- Nombre
- Total
- Pagado
- Pendiente
- Vencimientos
- Cuotas

No incluir domicilio, teléfono, notas internas ni datos laborales.

## Cambiar marca o WhatsApp

Editá `config.js`.

Para mostrar botón de WhatsApp, completá:

```js
whatsappNumber: "549XXXXXXXXXX"
```

Si lo dejás vacío, el botón no aparece.

## Cambiar la URL dentro de la app

Cuando tengas el link final de GitHub Pages, cargalo en la configuración de Préstamos Flash como URL del portal cliente.
