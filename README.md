# media-tag-sdk-android
mediatag sdk for android

В файл **settings.gradle** необходимо добавить следующий код:
```
 repositories {
        maven {url 'https://developer.huawei.com/repo/'}
        maven {
            url = uri("https://maven.pkg.github.com/cifrasoft/media-tag-sdk-android/")
            credentials {
                username "login"
                password "token" ///token должен быть сформирован с возможностью скачивания packages 
            }
        }
    }
```   


В файл **build.gradle(app)** необходимо добавить зависимости
```
    dependencies {
        implementation 'com.cifrasoft:mediatagsdk:1.0.1'
    }
```

Использование библиотеки:
```java
    Configuration configuration = new Configuration("partner_name", "tms"); //инициализация конфигурации
    Mediatag.instance(this).activate(configuration); //активация сервиса
    MediatagEvent event = new MediatagEvent(@NonNull MediatagEvent.ContactTypes type);  //инициализация события с одним обязательным параметром
    Mediatag.instance().addEvent(event); //добавляем событие в очередь для отправки

```
