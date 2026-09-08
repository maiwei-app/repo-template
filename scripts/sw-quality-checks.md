# Setup Custom-Stack CI

Cuando alguien te diga, literalmente, **"inicializa el CI de este repo"**, sigue esto:

- Lee la página de Notion "Calidad del Código" para tener el contexto de la política: https://app.notion.com/p/colomr/Calidad-del-C-digo-3d5c368461ee8126b387fb8329f703f6
- Haz una pregunta concreta: **¿qué lenguaje/framework es este repo?**
- Con la respuesta, mira el inventario real de `maiwei-app/workflows` (su README + la carpeta `.github/workflows/`, por si el README está desactualizado) y ve qué bloques ya existen para ese lenguaje.
- Si hay algo que no se puede deducir solo del lenguaje (¿necesita medir cobertura de tests? ¿tiene TOML? ¿lleva frontend?), pregúntalo — no lo asumas.
- Enseña el `ci.yml` completo que propones escribir, **antes de tocar nada.**
- Solo cuando el humano confirma, escríbelo de verdad.
