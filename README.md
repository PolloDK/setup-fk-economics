# Setup FK Economics: Claude Code en Windows

Esta guia deja un computador con Windows listo para trabajar con:

- Python
- VS Code
- extensiones base
- entornos virtuales
- Jupyter Notebook
- Claude Code

La idea es que, al terminar, tengas un flujo simple y estable:

1. abrir una carpeta de proyecto
2. crear y activar un entorno virtual
3. instalar paquetes con `pip`
4. trabajar en VS Code con el interprete correcto
5. usar notebooks y scripts Python
6. abrir `claude` desde la terminal y trabajar sobre el mismo proyecto

## Que es cada cosa

- `Python`: el lenguaje con el que vas a programar.
- `pip`: el gestor de paquetes de Python. Sirve para instalar librerias.
- `venv`: el entorno virtual de Python. Sirve para aislar dependencias por proyecto.
- `VS Code`: el editor/IDE donde vas a programar.
- `Jupyter Notebook`: cuadernos interactivos para probar codigo, analizar datos y documentar.
- `Node.js`: entorno de JavaScript. Hoy Claude Code en Windows se instala de forma nativa, pero Node sigue siendo util para herramientas del ecosistema y para muchos proyectos.
- `Git`: control de versiones. En Windows, Claude Code necesita `Git for Windows`.
- `Claude Code`: asistente de desarrollo en terminal para trabajar directamente sobre tu codigo.

## 🎯 Objetivo final

Al final de esta instalacion deberia funcionar todo esto en `CMD`:

```cmd
python --version
pip --version
node --version
git --version
claude --version
```

Y dentro de un proyecto deberia funcionar tambien:

```cmd
python -m venv .venv
.venv\Scripts\activate
python -m pip install --upgrade pip
pip install jupyter ipykernel
code .
claude
```

## 1. 🧰 Git for Windows

### Para que sirve

Git permite trabajar con repositorios. Ademas, Claude Code en Windows necesita `Git for Windows` para ejecutar su shell correctamente.

### Que hacer

1. Descarga Git for Windows desde:
   `https://git-scm.com/download/win`
2. Ejecuta el instalador.
3. Deja la configuracion por defecto salvo que ya tengas una preferencia clara.

### Verificacion

Abre `CMD` y ejecuta:

```cmd
git --version
```

Si responde con una version, Git quedo instalado.

## 2. 🐍 Python

### Para que sirve

Python es el lenguaje principal del entorno. Lo usaras para scripts, analisis, automatizaciones y notebooks.

### Recomendacion

Para un setup simple, instala Python desde la pagina oficial:

`https://www.python.org/downloads/windows/`

### Que hacer

1. Descarga la version estable actual para Windows.
2. Ejecuta el instalador.
3. Marca la opcion `Add python.exe to PATH`.
4. Completa la instalacion.

### Verificacion

Abre una nueva ventana de `CMD` y ejecuta:

```cmd
python --version
pip --version
```

Si `python` no responde, prueba tambien:

```cmd
py --version
```

## 3. 💻 VS Code

### Para que sirve

VS Code es el editor donde vas a escribir codigo, abrir notebooks, usar la terminal integrada y trabajar con Claude Code sobre el proyecto.

### Descarga

`https://code.visualstudio.com/download`

### Que hacer

1. Descarga la version para Windows.
2. Ejecuta el instalador.
3. Si aparece la opcion, deja habilitado agregar VS Code al `PATH`.

### Verificacion

En una nueva ventana de `CMD`:

```cmd
code --version
```

Si no funciona, no es grave: puedes abrir VS Code manualmente desde el menu Inicio.

## 4. 🧩 Extensiones basicas de VS Code

Estas extensiones dejan listo el entorno para Python, notebooks y una experiencia mas comoda.

### 4.1 Python

- Extension: `Python`
- Marketplace: `ms-python.python`
- Para que sirve: deteccion de interpretes, autocompletado, debugging, ejecucion y soporte general de Python.

### 4.2 Jupyter

- Extension: `Jupyter`
- Marketplace: `ms-toolsai.jupyter`
- Para que sirve: abrir y ejecutar notebooks `.ipynb` dentro de VS Code.

### 4.3 Prettier

- Extension: `Prettier - Code formatter`
- Marketplace: `esbenp.prettier-vscode`
- Para que sirve: formatear automaticamente JSON, Markdown, HTML, CSS y JavaScript.
- Nota: Prettier no es el formateador principal de Python.

### 4.4 Material Icon Theme

- Extension: `Material Icon Theme`
- Marketplace: `PKief.material-icon-theme`
- Para que sirve: mejora los iconos del explorador de archivos para ubicar carpetas y archivos mas rapido.

### Instalacion rapida desde VS Code

1. Abre VS Code.
2. Ve a `Extensions`.
3. Busca e instala:
   - `Python`
   - `Jupyter`
   - `Prettier - Code formatter`
   - `Material Icon Theme`

## 5. Node.js

### Para que sirve

Node.js no es obligatorio para usar Python, pero sigue siendo muy util:

- algunas herramientas de desarrollo lo usan
- Prettier y muchas utilidades del ecosistema web dependen de Node
- muchos proyectos modernos lo requieren aunque tu trabajo principal sea en Python

### Descarga

`https://nodejs.org/en/download`

### Recomendacion

Instala la version `LTS`.

### Verificacion

En `CMD`:

```cmd
node --version
npm --version
```

## 6. 🤖 Claude Code en Windows

### Importante

Segun la documentacion oficial actual, Claude Code en Windows se instala de forma nativa y requiere `Git for Windows`. Aunque tu terminal diaria sea `CMD`, Claude Code funciona mejor cuando tiene disponible ese entorno.

### Opcion recomendada: instalacion nativa

Abre `CMD` y ejecuta:

```cmd
curl -fsSL https://claude.ai/install.cmd -o install.cmd && install.cmd && del install.cmd
```

Cuando termine, cierra y vuelve a abrir `CMD`.

### Verificacion

```cmd
claude --version
claude doctor
```

### Primer inicio de sesion

Ejecuta:

```cmd
claude
```

Luego sigue el flujo de autenticacion.

### Que necesitas para entrar

Claude Code puede autenticarse, segun la configuracion de tu cuenta, con:

- `Claude App` usando una cuenta con plan compatible
- `Anthropic Console` con billing activo
- plataformas empresariales como `Amazon Bedrock` o `Google Vertex AI`

Para un video simple de setup personal, el flujo mas directo suele ser iniciar sesion al ejecutar `claude`.

## 7. Carpeta de trabajo

### Para que sirve

La idea es que cada proyecto tenga su propia carpeta y su propio entorno virtual.

### Ejemplo

```cmd
mkdir C:\Proyectos\demo-claude-code
cd C:\Proyectos\demo-claude-code
```

## 8. 📦 Entorno virtual de Python

### Para que sirve

El entorno virtual evita mezclar paquetes entre proyectos. Eso hace que el proyecto sea mas estable y reproducible.

### Crear el entorno

Dentro de tu carpeta de proyecto:

```cmd
python -m venv .venv
```

Esto crea una carpeta oculta llamada `.venv` con un Python aislado para ese proyecto.

### Activar el entorno en `CMD`

```cmd
.venv\Scripts\activate
```

Si todo salio bien, veras algo como esto al inicio de la linea:

```cmd
(.venv)
```

### Actualizar `pip`

```cmd
python -m pip install --upgrade pip
```

## 9. Paquetes base del entorno

### Minimo recomendado

Con el entorno virtual activado:

```cmd
pip install jupyter ipykernel
```

### Que instala esto

- `jupyter`: soporte para trabajar con notebooks
- `ipykernel`: permite que VS Code use ese entorno virtual como kernel del notebook

### Paquetes utiles para arrancar

Si quieres dejar una base un poco mas completa para clases o exploracion:

```cmd
pip install pandas matplotlib openpyxl requests python-dotenv
```

### Guardar dependencias

Cuando tengas el entorno listo:

```cmd
pip freeze > requirements.txt
```

## 10. Abrir el proyecto en VS Code

Con el entorno virtual activado y parado en la carpeta del proyecto:

```cmd
code .
```

Si `code .` no funciona, abre VS Code manualmente y luego `File > Open Folder`.

## 11. Conectar VS Code al entorno virtual correcto

Este paso es clave. Si VS Code usa otro Python, notebooks y scripts se van a ejecutar con el interprete equivocado.

### Que hacer

1. Abre la paleta de comandos con `Ctrl + Shift + P`.
2. Ejecuta `Python: Select Interpreter`.
3. Elige el interprete dentro de `.venv`.

Normalmente se vera parecido a esto:

```text
.venv\Scripts\python.exe
```

### Resultado esperado

- la terminal integrada reconoce el entorno
- VS Code ejecuta scripts con ese Python
- Jupyter usa el mismo kernel

## 12. 📓 Jupyter Notebook dentro de VS Code

### Crear un notebook

1. En VS Code, crea un archivo nuevo con extension `.ipynb`.
2. Cuando VS Code pida kernel, selecciona el Python de `.venv`.

### Si el kernel no aparece

Con el entorno activado, vuelve a ejecutar:

```cmd
pip install jupyter ipykernel
```

Luego reinicia VS Code.

### Que ganas con notebooks

- ejecutar codigo por bloques
- probar ideas rapido
- mezclar texto, resultados y graficos
- explicar procesos en clases o videos

## 13. Configurar la terminal de VS Code

### Recomendacion practica

Usa `Command Prompt` como terminal principal si tu flujo diario sera Python + `pip` + notebooks.

Pero deja `Git for Windows` instalado porque Claude Code lo necesita para funcionar bien en Windows.

### Dejar `CMD` como terminal por defecto

1. Abre VS Code.
2. Ve a `Terminal > Select Default Profile`.
3. Elige `Command Prompt`.

### Ajustes utiles de VS Code

Puedes agregar esto a tu configuracion de usuario:

```json
{
  "editor.formatOnSave": true,
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "python.terminal.activateEnvironment": true,
  "terminal.integrated.defaultProfile.windows": "Command Prompt"
}
```

### Nota importante sobre Prettier

Prettier sirve muy bien para `Markdown`, `JSON`, `HTML`, `CSS` y `JavaScript`.

Para Python, mas adelante puedes sumar `Ruff` o `Black` si quieres formateo y linting especifico del lenguaje.

## 14. Flujo recomendado de trabajo

Cada vez que empieces un proyecto nuevo:

1. crear carpeta del proyecto
2. abrir `CMD`
3. entrar a la carpeta
4. crear `.venv`
5. activar `.venv`
6. instalar dependencias con `pip`
7. abrir `code .`
8. seleccionar el interprete correcto
9. abrir `claude` en la terminal del proyecto

### Ejemplo completo

```cmd
mkdir C:\Proyectos\mi-proyecto
cd C:\Proyectos\mi-proyecto
python -m venv .venv
.venv\Scripts\activate
python -m pip install --upgrade pip
pip install jupyter ipykernel pandas matplotlib
code .
claude
```

## 15. ✅ Checklist final

En una terminal nueva, deberia funcionar:

```cmd
python --version
pip --version
node --version
git --version
claude --version
```

Dentro de un proyecto, deberia funcionar:

```cmd
python -m venv .venv
.venv\Scripts\activate
pip install jupyter ipykernel
code .
claude
```

En VS Code deberias poder:

- abrir un `.py`
- correr un script Python
- abrir un `.ipynb`
- seleccionar el kernel de `.venv`
- usar la terminal integrada con el entorno activado

## 16. 🛠️ Problemas comunes

### `python` o `pip` no se reconoce

Prueba estas acciones:

1. cerrar y volver a abrir `CMD`
2. revisar que Python se instalo con `Add to PATH`
3. probar `py --version`

### `code` no se reconoce

Opciones:

1. cerrar y volver a abrir la terminal
2. abrir VS Code manualmente desde Inicio
3. reinstalar VS Code dejando habilitada la opcion de `PATH`

### `claude` no se reconoce

Prueba:

1. cerrar y volver a abrir `CMD`
2. ejecutar de nuevo el instalador nativo
3. confirmar que `Git for Windows` esta instalado

### Claude abre, pero en Windows falla el shell

Claude Code en Windows depende de `Git for Windows`.

Si ves errores raros del shell:

1. confirma que Git esta instalado
2. actualiza Git for Windows
3. vuelve a abrir la terminal

### VS Code no detecta el entorno

1. activa `.venv` manualmente
2. ejecuta `Python: Select Interpreter`
3. elige `.venv\Scripts\python.exe`

### El notebook no encuentra kernel

Con `.venv` activado:

```cmd
pip install jupyter ipykernel
```

## 17. Estructura minima recomendada del proyecto

```text
mi-proyecto/
|-- .venv/
|-- notebooks/
|-- src/
|-- .gitignore
|-- README.md
|-- requirements.txt
```

## 18. Resumen corto para el video

Si quieres una version muy resumida del flujo:

1. instalar Git for Windows
2. instalar Python y dejar `PATH` activo
3. instalar VS Code
4. instalar extensiones `Python`, `Jupyter`, `Prettier` y `Material Icon Theme`
5. instalar Node.js LTS
6. instalar Claude Code con el instalador nativo
7. crear una carpeta de proyecto
8. crear y activar `.venv`
9. instalar `jupyter` e `ipykernel`
10. abrir `code .`
11. seleccionar el interprete de `.venv`
12. correr `claude`

## 🔗 Fuentes oficiales

- Anthropic Claude Code getting started:
  `https://docs.anthropic.com/en/docs/claude-code/getting-started`
- Anthropic Claude Code troubleshooting:
  `https://docs.anthropic.com/en/docs/claude-code/troubleshooting`
- Anthropic Claude Code settings:
  `https://docs.anthropic.com/en/docs/claude-code/settings`
- Python para Windows:
  `https://www.python.org/downloads/windows/`
- Python `venv`:
  `https://docs.python.org/3/library/venv.html`
- Visual Studio Code:
  `https://code.visualstudio.com/download`
- VS Code Python environments:
  `https://code.visualstudio.com/docs/python/environments`
- VS Code Jupyter:
  `https://code.visualstudio.com/docs/datascience/jupyter-notebooks`
- Node.js:
  `https://nodejs.org/en/download`
- Python extension:
  `https://marketplace.visualstudio.com/items?itemName=ms-python.python`
- Jupyter extension:
  `https://marketplace.visualstudio.com/items?itemName=ms-toolsai.jupyter`
- Prettier extension:
  `https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode`
- Material Icon Theme:
  `https://marketplace.visualstudio.com/items?itemName=PKief.material-icon-theme`
