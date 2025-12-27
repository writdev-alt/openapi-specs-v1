# WRPay API OpenAPI Specification

This repository contains the OpenAPI specification for WRPay - Secure Payments & Advanced Merchant Gateway API, organized using Redocly's multi-file structure.

## Structure

```
.
├── openapi.yaml              # Main OpenAPI file with references
├── redocly.yaml              # Redocly configuration
├── paths/                    # Individual path definitions
│   ├── initiate-payment-qris.yaml
│   ├── wallets.yaml
│   ├── wallet-details.yaml
│   ├── withdraw.yaml
│   ├── withdraw-reject.yaml
│   ├── check-status.yaml
│   ├── balance.yaml
│   ├── withdraw-accounts.yaml
│   ├── withdraw-accounts-methods.yaml
│   ├── withdraw-accounts-lists.yaml
│   ├── withdraw-accounts-info.yaml
│   └── withdraw-account-details.yaml
└── components/               # Reusable components
    ├── responses/           # Common response schemas
    │   ├── Unauthorized.yaml
    │   ├── ValidationError.yaml
    │   ├── InternalServerError.yaml
    │   └── ServiceUnavailable.yaml
    └── schemas/             # Reusable schema definitions (future use)
```

## Commands

- `npm run bundle` - Bundle all split files into a single `bundled.yaml` file
- `npm run lint` - Lint the OpenAPI specification
- `npm run preview` - Preview the documentation using Redocly preview (port 9000)
- `npm run build` - Bundle the spec and generate static HTML documentation
- `npm run build:html` - Generate static HTML documentation using Redoc (open-source)
- `npm run serve` - Serve the bundled spec using Redoc CLI (port 9000)

## Using Redoc (Open Source)

This project uses [Redoc](https://github.com/Redocly/redoc) (open-source) for generating beautiful, static HTML documentation. The project uses [Redocly CLI](https://redocly.com/docs/cli/) to manage the multi-file OpenAPI specification structure and build documentation.

### Building Documentation

To generate static HTML documentation:

```bash
npm run build
```

This will:
1. Bundle all split files into `bundled.yaml`
2. Generate a static HTML file in `dist/index.html` using Redoc (open-source)

The generated HTML file is self-contained and can be deployed to any static hosting service.

### Preview Documentation

To preview the documentation locally:

```bash
npm run preview
```

This starts a local preview server on port 9000 using Redocly preview.

