---
title: Конфигурация
---
Можно изменить настройки в файле `_config.yml`.

### Сайт

Настройки | Описание
--- | ---
`title` | Название сайта
`subtitle` | Подзаголовок сайта
`description` | Описание сайта
`author` | Ваше имя
`language` | Язык сайта. Используйте [2-значный код ISO-639-1](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes). По умолчанию: `en`.
`timezone` | Временной пояс. Hexo использует настройки компьютера по умолчанию. Список доступных часовых поясов можно найти [здесь](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones). Несколько примеров: `America/New_York`, `Japan` и `UTC`.

### URL

Параметр | Описание | Умолчание
--- | --- | ---
`url` | URL-адрес сайта |
`root` | Корневая папка сайта |
`permalink` | [Постоянная ссылка](permalinks.html) используются ссылки на статьи | `:year/:month/:day/:title/`
`permalink_defaults` | Значение по умолчанию для каждого сегмента постоянной ссылки |

{% note info Сайт в подпапке %}
Если ваш сайт располагается в поддиректории (к примеру `http://example.org/blog`) поменяйте значение `url` на `http://example.org/blog` и установите переменной `root` значение `/blog/`.
{% endnote %}

### Папки

Параметр | Описание | Умолчание
--- | --- | ---
`source_dir` | Папка с исходниками. Здесь хранится контент | `source`
`public_dir` | Папка публикации. Здесь хранится сгенерированный сайт | `public`
`tag_dir` | Папка с тегами | `tags`
`archive_dir` | Папка с архивами | `archives`
`category_dir` | Папка с категориями | `categories`
`code_dir` | Папка с кодом | `downloads/code`
`i18n_dir` | Папка  i18n | `:lang`
`skip_render` | Пути, которые исключены из обработки. Можно использовать [глобальные выражения](https://github.com/micromatch/micromatch#extended-globbing) для определения путей |

### Написание

Параметр | Описание | Умолчание
--- | --- | ---
`new_post_name` | Имя файла для создания новых постов | `:title.md`
`default_layout` | Макет по умолчанию | `post`
`titlecase` | Преобразовать заголовки в заглавные буквы? | `false`
`external_link` | Открывать внешние ссылки в новой вкладке? | `true`
`external_link.enable` | Открывать внешние ссылки в новой вкладке? | `true`
`external_link.field` | Applies to the whole `site` or `post` only | `site`
`external_link.exclude` | Exclude hostname. Specify subdomain when applicable, including `www` | `[]`
`filename_case` | Преобразовать имена файлов в `1` нижний регистр; `2` верхний регистр | `0`
`render_drafts` | Отображать черновики? | `false`
`post_asset_folder` | Включать [папку с материалами](asset-folders.html)? | `false`
`relative_link` | Создание ссылок относительно корневой папки? | `false`
`future` | Отображать будущие посты? | `true`
`highlight` | Настройки блоков кода |
`highlight.enable` | Enable syntax highlight | `true`
`highlight.auto_detect` | Enable auto-detection if no language is specified | `false`
`highlight.line_number` | Display line number | `true`
`highlight.tab_replace` | Replace tabs by n space(s); if the value is empty, tabs won't be replaced | `''`

### Категории и теги

Параметр | Описание | Умолчание
--- | --- | ---
`default_category` | Категория по умолчанию | `uncategorized`
`category_map` | Карта категорий |
`tag_map` | Карта тегов |

### Даты / Времени формат

Hexo использует [Moment.js](http://momentjs.com/) для работы с датами.

Параметр | Описание | Умолчание
--- | --- | ---
`date_format` | Формат даты | `YYYY-MM-DD`
`time_format` | Формат времени | `HH:mm:ss`
`use_date_for_updated` | Use the date of the post in [`post.updated`](/ru/docs/variables#Переменные-страницы) if no updated date is provided in the front-matter. Typically used with Git workflow | `true`

### Разбивка на страницы

Параметр | Описание | Умолчание
--- | --- | ---
`per_page` | Количество постов, отображаемых на странице. `0` отключает разбивку. | `10`
`pagination_dir` | Каталог разбивки | `page`

### Расширения

Параметр | Описание
--- | ---
`theme` | Имя темы. `false` отключает применение тем
`deploy` | Параметры публикации
`meta_generator` | [Meta generator](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meta#Attributes) tag. `false` disables injection of the tag.

### Incluir/Excluir Arquivos ou Diretórios

No arquivo de configuração, defina a chave de include/exclude para que o hexo processe ou ignore, explicitamente, determinados arquivos/diretórios.

`include` and `exclude` options only apply to the `source/` folder, whereas `ignore` option applies to all folders.

Configuração | Descrição
--- | ---
`include` | Por padrão, o Hexo ignora os arquivos e diretórios ocultos, mas configurar este campo fará com que o Hexo os processe também
`exclude` | O Hexo irá ignorar os arquivos e diretórios listados abaixo deste campo
`ignore` | Ignore files/folders

Exemplo:
```yaml
# Incluir/Excluir Arquivos/Diretórios
include:
  - ".nojekyll"
  # Include 'source/css/_typing.css'.
  - "css/_typing.css"
  # Include any file in 'source/_css/'.
  - "_css/*"
  # Include any file and subfolder in 'source/_css/'.
  - "_css/**/*"

exclude:
  # Exclude 'source/js/test.js'.
  - "js/test.js"
  # Exclude any file in 'source/js/'.
  - "js/*"
  # Exclude any file and subfolder in 'source/js/'.
  - "js/**/*"
  # Exclude any file with filename that starts with 'test' in 'source/js/'.
  - "js/test*"
  # Exclude any file with filename that starts with 'test' in 'source/js/' and its subfolders.
  - "js/**/test*"
  # Do not use this to exclude posts in the 'source/_posts/'.
  # Use skip_render for that. Or prepend an underscore to the filename.
  # - "_posts/hello-world.md" # Does not work.

ignore:
  # Ignore any folder named 'foo'.
  - "**/foo"
  # Ignore 'foo' folder in 'themes/' only.
  - "**/themes/*/foo"
  # Same as above, but applies to every subfolders of 'themes/'.
  - "**/themes/**/foo"
```

Each value in the list must be enclosed with single/double quotes.

`include:` and `exclude:` do not apply to the `themes/` folder. Either use `ignore:` or alternatively, prepend an underscore to the file/folder name to exclude.

\* Notable exception is the `source/_posts` folder, but any file or folder with a name that starts with an underscore under that folder would still be ignored. Using `include:` rule in that folder is not recommended.

### Usando uma Configuração Alternativa

Um arquivo de configuração personalizado pode ser especificado adicionando o sinalizador `--config` aos comandos do `hexo` com o caminho para o arquivo alternativo de configuração YAML ou JSON, ou até mesmo uma lista separada por vírgulas (sem espaços) de múltiplos arquivos YAML ou JSON.

``` bash
# usando 'custom.yml' no lugar de '_config.yml'
$ hexo server --config custom.yml

# usando 'custom.yml' e 'custom2.json', priorizando 'custom2.json'
$ hexo server --config custom.yml,custom2.json
```

O uso de vários arquivos combina todos os arquivos de configuração e salva as configurações mescladas para `_multiconfig.yml`. Os valores posteriores prevalecem. Este recurso funciona com qualquer quantidade de arquivos JSON e YAML com objetos arbitrariamente profundos. Observe que **nenhum espaço é permitido na lista**.

Por exemplo, no exemplo acima se `foo: bar` estiver em `custom.yml`, mas `"foo": "dinosaur"` estiver em `custom2.json`, `_multiconfig.yml` irá conter `foo: dinosaur`.

### Sobrescrevendo as Configurações do Tema

Os temas do Hexo são projetos independentes, com arquivos `_config.yml` separados.

Em vez de dar fork em um tema e manter uma branch personalizada com suas configurações, você pode configurá-lo a partir do arquivo de configuração principal do seu site.

Exemplo de configuração:

```yml
# _config.yml
theme_config:
  bio: "My awesome bio"
```

```yml
# themes/my-theme/_config.yml
bio: "Some generic bio"
logo: "a-cool-image.png"
```

Resultado da configuração do tema:

```json
{
  bio: "My awesome bio",
  logo: "a-cool-image.png"
}
```
