# Conventions du projet — site dominiquewils.fr

Ce fichier décrit les conventions de code à respecter sur ce projet.
Claude doit s'y conformer pour toute modification ou ajout de fichier.

## Bash

Convention de nommage des variables :

```bash
# Constantes : MAJUSCULES_AVEC_UNDERSCORES, déclarées en début de script
CONSTANTE="valeur"
DOMAIN_NAME="dominiquewils.fr"
DEFAULT_TIMEOUT=30

# Variables hors fonction (script-level) : minuscules_snake_case
var_not_in_function="valeur"
deployment_status="ok"
file_count=42

# Variables locales à une fonction : préfixées par un underscore
my_function() {
    local _var_in_function="valeur"
    local _local_path="/tmp/foo"
    local _result=0
}
```

**Récap** :

| Portée                | Style                       | Exemple                  |
|-----------------------|-----------------------------|--------------------------|
| Constante             | `MAJUSCULES_UNDERSCORE`     | `MAX_RETRIES`            |
| Variable hors fonction| `minuscules_snake_case`     | `current_branch`         |
| Variable dans fonction| `_minuscules_snake_case`    | `_temp_dir`              |

Les variables locales à une fonction doivent toujours être déclarées avec
`local` en plus du préfixe underscore.
