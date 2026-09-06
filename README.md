# aboutme-frontend

**About Me** — deployed at [aboutme.1ms.my](https://aboutme.1ms.my/).

Personal profile and downloadable CV for the 1ms.my platform.

## Stack

- Static HTML / CSS / vanilla JS
- nginx-unprivileged (Alpine), ~20 MB
- GitHub Actions → OCIR (linux/arm64)
- Flux Image Automation reconciles the tag bump back to [personal-k8s](https://github.com/AaronShemtov/personal-k8s)

## Shared style

The 1ms.my sites, including aboutme.1ms.my, infra.1ms.my and pwd.1ms.my, share the same `blueprint.css` visual language.

## Local preview

```bash
cd public
python3 -m http.server 8000
# open http://localhost:8000
```

## License

MIT.
