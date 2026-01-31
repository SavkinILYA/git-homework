# git-homework
Курс DevOps от Netology 2026
Показываю навыки владения гит

## .gitignore
В репозитории добавлены два файла .gitignore:

1. Корневой `.gitignore`  
2. Специализированный `.gitignore` внутри каталога `terraform/`

### Что игнорируется благодаря этим правилам

#### Корневой .gitignore
- все файлы и папки, начинающиеся с точки и заканчивающиеся на `.swp`, `.swo`, `.swn` (временные файлы vim/vim-подобных редакторов)
- файлы `*.bak`, `*.backup`, `*.old`
- директории `node_modules/`, `vendor/`, `__pycache__/`, `.pytest_cache/`, `.mypy_cache/`, `.ruff_cache/`
- файлы `.DS_Store`, `Thumbs.db`, `.env`, `.env.local`, `.env.*.local` (локальные переменные окружения)
- логи и временные файлы: `*.log`, `npm-debug.log*`, `yarn-debug.log*`, `yarn-error.log*`

#### terraform/.gitignore
- все директории `.terraform/` и `.terraform.lock.hcl` в любом месте проекта
- все файлы с расширениями `.tfstate`, `.tfstate.backup`, `.tfstate.*`
- файлы crash.log и crash.*.log
- все файлы с расширениями `.tfvars`, `.tfvars.json` (обычно содержат чувствительные данные)
- файлы override.tf, override.tf.json, *_override.tf, *_override.tf.json
- файлы конфигурации CLI: `.terraformrc`, `terraform.rc`

Примеры правил в terraform/.gitignore и их смысл:

- `**/.terraform/*` → игнорируются все файлы и папки внутри любой директории с именем `.terraform`
- `*.tfstate` → игнорируются все файлы, у которых расширение `.tfstate`
- `*.tfstate.*` → игнорируются все файлы, у которых где-то в имени есть `.tfstate.`
- `crash.log` → игнорируется файл с точным именем `crash.log`
- `crash.*.log` → игнорируются файлы вида `crash.что угодно.log`
- `*.tfvars` → игнорируются все файлы с расширением `.tfvars`
- `override.tf` → игнорируется файл с точным именем `override.tf`
- `*_override.tf` → игнорируются файлы, заканчивающиеся на `_override.tf`
