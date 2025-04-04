# Setup Node.js Project Action

Cette action permet de configurer rapidement un projet Node.js en installant la version spécifiée de Node.js et en installant les dépendances avec le gestionnaire de paquets de votre choix.

## Utilisation

```yaml
- uses: ./.github/actions/setup-node-project
  with:
    working-directory: './mon-projet'  # Optionnel, par défaut: '.'
    node-version: '22'                # Optionnel, par défaut: '22'
    package-manager: 'npm'            # Optionnel, par défaut: 'npm'
    cache-key: 'npm'                  # Optionnel, par défaut: 'npm'
```

## Inputs

| Input | Description | Requis | Valeur par défaut |
|-------|-------------|--------|------------------|
| `working-directory` | Répertoire de travail pour l'installation | Non | '.' |
| `node-version` | Version de Node.js à utiliser | Non | '22' |
| `package-manager` | Gestionnaire de paquets (npm, yarn, pnpm) | Non | 'npm' |
| `cache-key` | Clé de cache à utiliser | Non | 'npm' |

## Exemples

### Installation avec npm
```yaml
- uses: ./.github/actions/setup-node-project
  with:
    working-directory: './client'
    package-manager: 'npm'
```

### Installation avec yarn
```yaml
- uses: ./.github/actions/setup-node-project
  with:
    working-directory: './server'
    package-manager: 'yarn'
    cache-key: 'yarn'
```

### Installation avec pnpm
```yaml
- uses: ./.github/actions/setup-node-project
  with:
    working-directory: './api'
    package-manager: 'pnpm'
    cache-key: 'pnpm'
``` 