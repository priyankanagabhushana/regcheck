# RegCheck project overview

RegCheck is an AI-assisted comparison service for preregistrations, clinical-trial registrations, preclinical registrations, and published papers. It combines a FastAPI application, background task processing, parsers, and a browser interface.

## Comparison flow

1. Accept registration and publication inputs.
2. Normalize documents into comparable fields.
3. Run deterministic and model-assisted comparison dimensions.
4. Preserve quoted evidence and source locations in the result.
5. Present findings for human verification and export.

## Runtime components

- `backend/` contains routes, services, workers, and the command-line flow.
- `templates/` and `static/` provide the web interface.
- Redis stores task state for the asynchronous web path.
- `benchmarks/` and `tests/` support repeatable checks.

## Responsible use

The service is a research prototype, not a compliance certification system. A flagged change requires review of the underlying sources and relevant amendments. Use public or de-identified documents and avoid uploading sensitive patient information.

## Development notes

The CLI can run without Redis for backend experiments. The web path uses the environment settings documented in `.env.example` and `SECURITY.md`.
