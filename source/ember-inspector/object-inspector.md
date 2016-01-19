Inspector имеет панель, которая позволяет просматривать и взаимодействовать с объектами Ember. Чтобы открыть ее, щелкните на любой объект Ember. После этого вы можете просматривать свойства объектов.

### Просмотр объектов

Вот, что вы увидите, когда щелкните по объекту:

<img src="/static/images/guides/ember-inspector/object-inspector-controller.png" width="450">

Inspector отображает родительские объекты и миксины, которые входят в состав выбранного объекта, включая унаследованные свойства.

Каждое значение свойства в этом представлении связано с приложением, поэтому если значение свойства в приложении обновляется, то это будет отражено в Inspector.

Если перед именем свойства стоит иконка калькулятора, то — это [вычислительное свойство](http://emjs.ru/v2/object-model/computed-properties). Если значение вычислительного свойства еще не указано, вы можете щелкнуть на иконку калькулятора, чтобы исправить это.

### Вывод объектов на консоль

#### Отправка из INSPECTOR на консоль

Вы можете вывести объекты на консоль, если щелкните в Inspector на кнопку `$E`. Так вы установите глобальную переменную `$E` на выбранный объект.

<img src="/static/images/guides/ember-inspector/object-inspector-$E.png"
width="450">

Вы также можете вывести на консоль свойства. Когда вы наведете курсор на свойства объекта, рядом с каждым из них будет появляться кнопка `$E`. Щелкните на нее, чтобы вывести значение свойства на консоль.

<img src="/static/images/guides/ember-inspector/object-inspector-property-$E.png" width="450">

#### Отправка из консоли в INSPECTOR

Вы можете отправить объекты и массивы Ember в Inspector с помощью `EmberInspector.inspect` в консоли.

```js
var object = Ember.Object.create();
EmberInspector.inspect(object);
```

Убедитесь, что Inspector активен, когда будете вызывать этот метод.

### Редактирование свойств

Вы можете редактировать в Inspector свойства `String`, `Number` и `Boolean`. Изменения будут сразу отражены в приложении. Щелкните на значение свойства, чтобы начать редактирование.

<img src="/static/images/guides/ember-inspector/object-inspector-edit.png"
width="450">

Отредактируйте свойство и нажмите клавишу `ENTER`, чтобы подтвердить изменения, или клавишу `ESC`, чтобы отменить их.

### Навигация по INSPECTOR

Помимо просмотра свойств выше, вы можете проделывать то же самое со свойствами объектов и массивов Ember.

<img src="/static/images/guides/ember-inspector/object-inspector-object-property.png" width="450">

Через Inspector вы можете продолжать углубляться в свойства объекта или массива Ember. На изображении ниже мы сначала щелкнули по свойству `model`, а затем по свойству `store`.

<img src="/static/images/guides/ember-inspector/object-inspector-nested-objects.png" width="450">

Тут вы можете видеть путь к текущему объекту на самом верху Inspector. Можно вернуться к предыдущему объекту, если щелкнуть стрелочку вверху слева.

### Индивидуальное группирование свойств

Некоторые свойства группируются не только по наследованию, но и по семантике уровней фреймворка. Например, если вы просматриваете модель Ember Data, то можете видеть группы `Attributes`, `Belongs To`, `Has Many` и `Flags`.

<img src="/static/images/guides/ember-inspector/object-inspector-model.png" width="450">

Авторы библиотек могут индивидуально настраивать отображение любого объекта в Inspector. С помощью метода `_debugInfo` объект может сообщить Inspector, как его необходимо отобразить. Чтобы просмотреть примеры настройки свойств объектов, загляните в раздел [настройки Ember Data](https://github.com/emberjs/data/blob/f1be2af71d7402d034bc034d9502733647cad295/packages/ember-data/lib/system/debug/debug_info.js).