# V2: Требования к конфиденциальности и хранению данных

## Цель проверки

Защита конфиденциальных данных, таких как учетные данные пользователя и конфиденциальная информация, является ключевым аспектом безопасности мобильных устройств. Во-первых, конфиденциальные данные могут непреднамеренно быть раскрыты другим приложениям, работающим на том же устройстве, если механизмы операционной системы, такие как механизм межпроцессного взаимодействия(IPC), используются ненадлежащим образом. Данные также могут непреднамеренно попасть в облачное хранилище, резервную копию или кеш клавиатуры. Кроме того, мобильные устройства могут быть потеряны или украдены легче чем другие типы устройств, поэтому более вероятным сценарием является злоумышленник, получающий физический доступ. В этом случае могут быть реализованы дополнительные меры защиты, чтобы затруднить получение конфиденциальных данных.

Обратите внимание, что, поскольку MASVS ориентирован на приложения, он не охватывает политики безопасности на уровне устройств, такие как те, которые применяются решениями MDM(Mobile Device Managment). Мы поощряем использование таких политик в контексте предприятия для дальнейшего повышения безопасности данных.

### Определение чувствительных данных

К чувствительным данным, в контексте MASVS, относятся как учетные записи пользователя, так и  любые другие данные, которые считаются чувствительными в конкретном контексте, например:

- Личная информация (PII), которая может быть использована для кражи личных данных: номера социального страхования, номера кредитных карт, номера банковских счетов, информация о здоровье.
- Высокочувствительные данные, которые могут привести к репутационному ущербу и/или финансовым потерям, если они скомпрометированы: информация о договорах, информация, охватываемая соглашениями о неразглашении данных, управленческая информация;
- Любые данные, которые должны быть защищены законом или по причине предъявленных внутренних/внешних требований.

## Требования к верификации безопасности

Подавляющее большинство проблем с раскрытием информации можно предотвратить, следуя простым правилам. Большинство требований, перечисленных в этой главе, являются обязательными для всех уровней проверки.

| # | Описание | L1 | L2 |
| --- | --- | --- | --- |
| **2.1** | Системные хранилиша данных используются надлежащим образом для хранения конфиденциальных данных, таких как учетные данные пользователя или криптографические ключи. | ✓ | ✓ |
| **2.2** | Чувствительная информация должна храниться либо внутри контейнера приложения либо же в системном хранилище. | ✓ | ✓ |
| **2.3** | Чувствительная информация не записывается в лог приложения. | ✓ | ✓ |
| **2.4** | Никакие конфиденциальные данные не передаются третьей стороне, если это не является необходимой частью архитектуры. | ✓ | ✓ |
| **2.5** | Кэш клавиатуры выключен в полях ввода чувствительной информации. | ✓ | ✓ |
| **2.6** | Чувствительные данных недоступны для механизмов межпроцессного взаимодействия(IPC). | ✓ | ✓ |
| **2.7** | Никакие конфиденциальные данные, такие как пароли или контакты не видны через пользовательский интерфейс. | ✓ | ✓ |
| **2.8** | Никакие конфиденциальные данные не включены в резервные копии, созданные мобильной операционной системой. |   | ✓ |
| **2.9** | Приложение скрывает конфиденциальные данные с экрана(views), когда находится в фоновом режиме. |  | ✓ |
| **2.10** | Приложение не хранит конфиденциальные данные в памяти дольше, чем необходимо, и память очищается явно после использования. |  | ✓ |
| **2.11** | Приложение использует минимальную политику безопасности доступа к устройству, например, требуя от пользователя установить пароль для устройства. |  | ✓ |
| **2.12** | Приложение информирует пользователя о типах обрабатываемой персональной информации, а также о лучших приктиках безопасности, которым должен следовать пользователь при использовании приложения. |  | ✓ |

## Ссылки

OWASP MSTG содержит подробные инструкции по верификации требований, перечисленных в этом разделе.

- Для Android - https://github.com/OWASP/owasp-mstg/blob/master/Document/0x05d-Testing-Data-Storage.md
- Для iOS - https://github.com/OWASP/owasp-mstg/blob/master/Document/0x06d-Testing-Data-Storage.md

Для получения дополнительной информации смотрите также:

- OWASP Mobile Top 10: M2  - Insecure Data Storage: https://www.owasp.org/index.php/Mobile_Top_10_2016-M2-Insecure_Data_Storage
- CWE: https://cwe.mitre.org/data/definitions/922.html
