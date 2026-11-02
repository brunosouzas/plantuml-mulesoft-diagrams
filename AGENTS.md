# plantuml-mulesoft-diagrams: project context

## Purpose

Repository containing MuleSoft-related PlantUML sources and technical documentation under plantUML/ and techDocs/. No root README defines a wider application purpose.

## Technology

Stack: PlantUML, MkDocs (Backstage TechDocs), GitHub Actions
Delivery: E reference
Model: reference
Integration branch: `main`
Data: none
Article: none

- Build: point `!define pathLibrary` at `plantUML/library/brunosouzas` in the checkout first, as ci.yml does, then `java -jar plantuml-1.2026.9.jar -Playout=smetana -tsvg -failfast2 <diagram>.puml` (CI renders every `.puml` with `@startuml` and every library fragment, the library pointed at this checkout: `.github/workflows/ci.yml`)
- Test: same as Build: a syntax error fails the render
- Run locally: `not applicable`
- Deliver and verify: `nothing is deployed; CI green on the merge commit`

## Technology declarations

No framework or interpreter version is pinned by the root manifests inspected. Check the task-specific source before selecting a runtime.

These are source declarations, not evidence of installed runtimes. Maven properties may describe build/test dependencies rather than supported runtime minima; unresolved expressions remain inherited until verified.

## Layout and operation sources

Top-level source/documentation directories: `capability`, `plantUML`, `techDocs`.



GitHub default branch inspected on 2026-10-06: `main`. Release bases are defined by the project sources, separately from that setting. Build/publish commands mentioned by those sources are context, not authorization.

## Project rules

Before planning, reviewing or changing this project, read [the applicable project rules](rules/README.md).

- Board area: `mulesoft` (Azure Boards, project `brunosouzas`).
- OpenSpec: no: every change takes the small path.
- Releases: none. When an article cites a version, Bruno creates an `article-<slug>` tag (not `v*`).
- The library files under `plantUML/library/brunosouzas/` are `!include` fragments. CI renders every fragment, wrapped in a diagram that includes it (after `GeneralCommon.puml` for the `dist/` ones, which build on it), and every sample; `sample/mulesoft apis local.puml` includes them from a local path and `sample/mulesoft_apis.puml` from the old `brunosouzas/diagrams` URL.
