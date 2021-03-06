# ControlValidation

Этот каталог содержит пример валидации данных.
Выполнить проверку, что заполнено определенное текстовое поле и количество символов не превышает 100.

## Настройка среды

**Перечень необходимых инструментов:** 
* [Visual Studio](https://www.visualstudio.com)
* [TypeScript 2.2](https://www.typescriptlang.org)
* Включенные в **Visual Studio** опции  [NuGet Package Restore](https://docs.microsoft.com/en-us/nuget/consume-packages/package-restore#enabling-and-disabling-package-restore)

## Сборка и установка

1. Открыть /Samples.sln
2. Собрать проект ClientScripts > ControlValidation > ControlValidationWebExtension
3. Скопировать каталог SamplesOutput\Site\Content\Extensions\ControlValidation в каталог "Путь к установленному Web-клиент\Site\Content\Extensions"
4. Перезапустить IIS

## Проверка примера

1. Запустить конструктор разметок
2. Импортировать разметку из файла ControlValidationLayout.xml без условий использования. При этом будет добавлена разметка в тип карточки документ, вид ДокументУД\Исходящий
3. Задать для разметки условия использования, поменяв также порядок разметок в условиях использования, чтобы разметка стала первой разметкой для редактирования 
4. На разметке расположен textBox и кнопки сохранения/отмены
5. Перезапустить IIS
6. Открыть документ ДокументУД\Исходящий и нажать кнопку редактировать. При этом должна открыться разметка с textBox и кнопками сохранения
7. Если в textBox нет текста или длина текста превышает 100 символов, то при нажатии кнопки сохранить возникает сообщение об ошибке и изменения не сохраняются

## Проект ControlValidationWebExtension

Проект-расширение клиентской части Web-клиент. Содержит клиентский скрипт c функцией validateTextBoxControl, реализующей валидацию данных контрола.

Внимание! Данный пример демонстрирует только доступ к элементу разметки. 
При реализации расширений рекомендуется использовать экспорт разметок в виде Решения.