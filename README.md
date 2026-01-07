# bkstg-demo-external

External demo catalog for [bkstg](https://github.com/i2y/bkstg).

This repository demonstrates how team-specific catalogs can be referenced from a central repository via Location entities.

## Contents

- `catalogs/components/payment-service.yaml` - Payment service component
- `catalogs/components/notification-service.yaml` - Notification service component
- `catalogs/apis/payment-api.yaml` - Payment API definition

## How It Works

The main [bkstg-demo](https://github.com/i2y/bkstg-demo) repository contains a Location entity that references this repository:

```yaml
apiVersion: backstage.io/v1alpha1
kind: Location
metadata:
  name: external-team-catalog
spec:
  type: url
  targets:
    - https://github.com/i2y/bkstg-demo-external/blob/main/catalogs/components/payment-service.yaml
```

When bkstg loads the main demo, it automatically clones this repository and makes all entities editable.

## License

MIT
