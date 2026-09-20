# AGENTS.md

Estas reglas aplican a los cambios en public_rep.

## Ramas y flujo

- `main` es la rama de integración activa y la rama desde la que el usuario trabaja y prueba.
- `master` es un snapshot estable/promocionado. No se sincroniza automáticamente con `main`.
- Para trabajo relevante, parte del `main` actual, usa una rama/PR por responsabilidad coherente y ejecuta comprobaciones locales/dirigidas razonables.
- Fusiona la PR a `main` sin esperar a que termine la CI remota.
- No obligues al usuario a cambiar de rama para probar.
- Si existe CI, debe ejecutarse por defecto post-merge sobre `main`, no duplicarse en PR.
- No configures CI automática para `master`.
- No hagas polling repetitivo de CI/deploy. Revísalo en un punto natural posterior o en la siguiente iteración y corrige prioritariamente los fallos relacionados.
- Si ya conoces un fallo antes del merge por una comprobación local/dirigida, corrígelo primero.
- Promueve `main -> master` solo cuando el usuario pida fijar explícitamente una versión estable.

## Trabajo en el repo

- Lee README, `/docs` y las instrucciones específicas existentes antes de cambios relevantes.
- Mantén cambios cohesionados y actualiza tests/documentación cuando corresponda.
- No guardes secretos, tokens ni credenciales.
