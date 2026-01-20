# Day 14 – Kubernetes ConfigMaps & Secrets

## Why Externalize Configuration?
Keeping config outside the image allows:
- Same image across environments
- No rebuilds for config changes
- Better security & flexibility

Rule:
Code changes → new image
Config changes → update ConfigMap/Secret

---

## ConfigMap
ConfigMap stores non-sensitive configuration data.

Use cases:
- App environment (DEV/PROD)
- Feature flags
- Service URLs

---

## Create ConfigMap (YAML)
apiVersion: v1
kind: ConfigMap
metadata:
  name: app-config
data:
  APP_ENV: production
  APP_DEBUG: "false"

---

## Using ConfigMap as Environment Variables
spec:
  containers:
    - name: app
      image: nginx
      envFrom:
        - configMapRef:
            name: app-config

---

## Secrets
Secrets store sensitive data securely.

Examples:
- DB passwords
- API keys
- Tokens

Values are base64-encoded.

---

## Create Secret (YAML)
apiVersion: v1
kind: Secret
metadata:
  name: app-secret
type: Opaque
data:
  DB_PASSWORD: cm9vdA==

(Note: 'root' encoded in base64)

---

## Using Secret as Environment Variables
spec:
  containers:
    - name: app
      image: nginx
      envFrom:
        - secretRef:
            name: app-secret

---

## ConfigMap & Secret as Volumes
They can be mounted as files inside containers.

Useful when apps read config files.

---

## Best Practices
- Never commit secrets to Git
- Use different configs per environment
- Rotate secrets regularly
- Use RBAC to limit access

---

## What I Learned Today
- Externalized configuration
- ConfigMaps vs Secrets
- Injecting config into pods
- Secure app configuration

---

## Interview Notes
- ConfigMaps store non-sensitive data
- Secrets store sensitive data
- Both decouple config from code
- Essential for production security
