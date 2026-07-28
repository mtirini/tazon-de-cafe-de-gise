# Cómo publicar el sitio y activar tu panel privado de edición

Estos son los pasos para subir "Tazón de Café" a internet con Netlify, y dejar activo tu panel privado en `/admin` donde vas a poder agregar, editar o borrar fotos y descripciones vos sola, sin que el público lo vea.

## 1. Crear una cuenta en GitHub (si no tenés)

Andá a github.com y creá una cuenta gratis con tu email.

## 2. Crear el repositorio con los archivos del sitio

1. En GitHub, creá un repositorio nuevo (por ejemplo `tazon-de-cafe`). Puede ser privado o público, no afecta el funcionamiento del sitio.
2. Subí a ese repositorio **todos los archivos de esta carpeta**, incluyendo:
   - `index.html`
   - `productos.json`
   - la carpeta `admin/` completa (con `index.html` y `config.yml` adentro)
   - `.gitignore`
   - **todas las fotos .jpg** que ya tenías (deben quedar en la raíz del repositorio, junto a `index.html`)
3. La forma más simple de subir todo es arrastrando los archivos a la página del repositorio en GitHub ("Add file" → "Upload files"), sin necesidad de usar la terminal.

## 3. Conectar el repositorio a Netlify

1. Andá a netlify.com y creá una cuenta gratis (podés entrar directo con tu cuenta de GitHub).
2. "Add new site" → "Import an existing project" → elegí GitHub → seleccioná el repositorio que subiste.
3. Dejá los campos de "Build command" vacíos y "Publish directory" como `/` (la raíz) — es un sitio estático, no necesita build.
4. Hacé clic en "Deploy site". En un minuto vas a tener una URL tipo `nombre-al-azar.netlify.app` funcionando.
5. Opcional: en "Site settings" → "Domain management" podés cambiar ese nombre por algo como `tazondecafe.netlify.app`, o conectar un dominio propio si comprás uno.

## 4. Activar el login privado (Identity)

1. En el panel de Netlify de tu sitio: "Site settings" → "Identity" → "Enable Identity".
2. Bajá hasta "Registration preferences" y cambiala a **"Invite only"** — así nadie puede crearse una cuenta por su cuenta, solo vos podés invitar gente.
3. Bajá hasta "Services" → "Git Gateway" → "Enable Git Gateway". Esto es lo que permite que el panel guarde los cambios en GitHub sin que tengas que manejar tokens ni contraseñas de GitHub.

## 5. Invitarte a vos misma

1. En "Identity" → "Invite users", escribí tu email (mtirini@gmail.com).
2. Te va a llegar un correo de Netlify con un link de invitación. Al hacer clic, te lleva al sitio, te pide que elijas una contraseña, y automáticamente te redirige al panel `/admin`.
3. A partir de ahí, para volver a entrar simplemente vas a `tu-sitio.netlify.app/admin` e iniciás sesión con ese email y contraseña.

## 6. Usar el panel

Adentro de `/admin` vas a ver la lista completa de productos con su categoría, título, descripción y foto. Podés:
- **Agregar** un producto nuevo (botón para agregar un ítem a la lista, subís la foto directo desde tu computadora).
- **Editar** cualquier título, descripción, categoría o cambiar la foto.
- **Borrar** un producto.

Cada vez que hacés clic en "Guardar" / "Publish", el cambio se guarda en GitHub y Netlify vuelve a publicar el sitio automáticamente — en 1 o 2 minutos el cambio ya se ve en la web, sin que vos tengas que tocar código ni pedirme nada a mí.

## Importante sobre la privacidad

- El panel `/admin` no aparece en ningún menú ni link del sitio público — solo quien conoce esa dirección y tiene una cuenta invitada puede entrar.
- Solo tu email va a estar invitado, así que sos la única que puede loguearse y editar.
- Esto no es "seguridad bancaria": es la protección estándar que usan sitios chicos como este (login real con contraseña, no un simple candado). Para una página de productos de una pastelería es más que suficiente.
