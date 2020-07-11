# Based on https://github.com/appsembler/tahoe-lti

##Настройки UrFU для LTI Consumer XBlock: дополнительные поля команды и пользователя.

Этот пакет использует интерфейс LTI Consumer XBlock для добавления дополнительных параметров в дополнение к параметрам LTI по умолчанию.

## Использование

```
$ pip install git+https://github.com/MasterGowen/urfu-lti.git
```

Добавьте следующие настройки:

```python
EDXAPP_XBLOCK_SETTINGS = {
   "lti_consumer":
      {"parameter_processors":
          [
          'urfu_lti.processors:basic_user_info',
          'urfu_lti.processors:personal_user_info',
          'urfu_lti.processors:cohort_info',
          'urfu_lti.processors:team_info'
          ]
       }
  }
 
```

**Важно!** 
И `` basic_user_info``, и `` personal_user_info`` отправляют личную информацию о пользователях потенциальным сторонним поставщикам LTI.
Убедитесь, что это отражено в Политике конфиденциальности.