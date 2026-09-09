---
name: setup-custom-stack-ci
description: >
  Guía al modelo para inicializar el CI "Custom Stack" de un repo maiwei-app
  nuevo o sin inicializar. Se activa cuando alguien dice "inicializa el CI
  de este repo" o equivalente.
---

# Setup Custom-Stack CI

## Por qué existe esto
`ruleset-tag` no fuerza nada por sí sola — es solo una etiqueta. Sin este
flujo, cada repo termina con el CI que alguien le puso a mano, cuando tuvo
tiempo. Este documento es el mecanismo que sustituye esa memoria.

## Instrucciones

1. Lee la página de Notion "Calidad del Código" antes de nada:
   https://app.notion.com/p/colomr/Calidad-del-C-digo-3d5c368461ee8126b387fb8329f703f6
2. Pregunta, en una sola pregunta concreta: **¿qué lenguaje/framework es
   este repo?** No lo deduzcas del nombre ni de archivos existentes.
3. Con la respuesta, mira el inventario real en `maiwei-app/workflows`
   (su README **y** la carpeta `.github/workflows/` — el README puede
   estar desactualizado) y decide qué bloques ya construidos aplican.
4. Si algo no se deduce solo del lenguaje (¿cobertura de tests? ¿TOML?
   ¿frontend?), pregúntalo. No lo asumas por defecto.
5. Muestra el `ci.yml` completo que propones escribir, **antes de tocar
   nada del repo.**
6. Solo tras confirmación explícita, escribe el archivo real, y fija
   `ruleset-tag` con el valor que corresponda (`python-testing`,
   `flutter-testing`, `hugo-build` o `none`). Si el ruleset de
   organización "Custom Stack — `<ruleset-tag>`" para ese valor no existe
   todavía, no lo crees ni lo intentes tú — pídeselo explícitamente a
   quien lo pidió: el alta de un ruleset nuevo la decide y ejecuta él, no
   el modelo.

## Qué no hacer
- No asumas el stack ni los checks sin preguntar.
- No escribas `ci.yml` sin mostrarlo antes.
- No pongas `sw-checks-init=true` solo porque `ci.yml` esté escrito.

## Definición de Hecho (no presumida)
- `ci.yml` escrito con los checks reales del stack elegido.
- El ruleset de organización "Custom Stack — `<ruleset-tag>`" para ese
  stack existe y fue probado por fallo deliberado — si no existe, se crea
  primero, no es una excepción.
- Solo entonces, `sw-checks-init` del repo pasa a `true`.
