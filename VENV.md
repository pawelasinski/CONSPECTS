https://docs-python.ru/standart-library/modul-venv-python/

### Создание виртуальной среды

В виртуальную среду установится системная версия Python, т.е. версия установленная по умолчанию в вашей системе:

```zsh
python3 -m venv /path/to/<env_name> --prompt Python3.9
```

```PowerShell
python3 -m venv c:\path\to\<env_name> --prompt Python3.9
```

```PowerShell
c:\Python39\python -m venv c:\path\to\<env_name> --prompt Python3.9
```
	Если не настроены переменные PATH и PATHEXT для установки Python.


В виртуальную среду установится версия Python, расположенная по пути `/opt/python-3.11.0/bin/python3.11`:

```zsh
/opt/python-3.11.0/bin/python3.11 -m venv ~/.python3.11.0 --prompt Python3.11
```

Аналогично для Windows-платформ.


Для venv может быть задано несколько путей, и в этом случае будет создана идентичная виртуальная среда в соответствии с заданными параметрами для каждого указанного пути.


Представленная выше команда создает целевой каталог `environment`, создавая все не существующие родительские каталоги. После этого python поместит в него файл `pyvenv.cfg` с ключом, который будет указывать на ту версию Python, для которой запущена эта команда. Она также создает подкаталог `bin` в Unix или `Scripts` в Windows, содержащий копию/символическую ссылку двоичных файлов Python в зависимости от платформы или аргументов, используемых во время создания среды. Вышеуказанная команда также создает изначально пустой подкаталог `lib/pythonX.Y/site-packages` в Unix, в Windows это `Lib\\site-packages`. Если указан существующий каталог виртуальной среды, то он будет использован повторно.


```zsh
python3 -m venv -h
# usage: venv [-h] [--system-site-packages] [--symlinks | --copies] [--clear] 
#             [--upgrade] [--without-pip] [--prompt PROMPT] 
#             ENV_DIR [ENV_DIR ...]
```

Позиционные аргументы:

- `ENV_DIR` — каталог для создания виртуальной среды.

Необязательные аргументы:

- `-h`, `--help` — показать справочное сообщение и выйти.
- `--system-site-packages` — предоставляет виртуальной среде доступ к системным пакетам site-packages (по умолчанию не предоставляется).
- `--symlinks` — при установке виртуальной среды создает символические ссылки вместо копирования файлов.
- `--copies` — при установке виртуальной среды копирует файлы вместо создания символических ссылок.
- `--clear` — перед созданием виртуальной среды удаляет содержимое каталога, если он уже существует.
- `--upgrade` — обновите каталог виртуальной среды, чтобы использовать установленную версию Python.
- `--without-pip` — пропускает установку или обновление pip в виртуальной среде (pip загружается по умолчанию).
- `--prompt PROMPT` — предоставляет альтернативный префикс приглашения для этой среды.

### Запуск виртуальной среды

| Оболочка | Команда активации виртуальной среды |
|:-------------:| :-----| 
| bash/zsh | $ source <env_name>/bin/activate | 
| cmd.exe | C:> <env_name>\\Scripts\\activate.bat |
| PowerShell | PS C:> <env_name>\\Scripts\\Activate.ps1 |

```zsh
source ~/<env_name>/bin/activate
```

```zsh
deactivate
```

Не нужно специально активировать среду, если сценарий запускается с указанием полного пути до интерпретатора Python, установленного в виртуальную среду.