



``` bsl

// Преобразует объект XDTO чека в XML.
//
// Параметры:
//  ОбъектXDTO - ОбъектXDTO - Объект XDTO
//  ПространствоИмен - Строка - Имя пространства имен.
//  ИмяТипа - Строка - Имя типа
// 
// Возвращаемое значение:
//  Строка - Текст сообщения XML.
//
Функция ЧекXDTOВXML(ОбъектXDTO, ПространствоИмен, ИмяТипа) Экспорт
	
	ЗаписьXML = Новый ЗаписьXML;
	ЗаписьXML.УстановитьСтроку("UTF-8");
	
	ФабрикаXDTO.ЗаписатьXML(ЗаписьXML, ОбъектXDTO, ИмяТипа);
	
	ТекстXML = ЗаписьXML.Закрыть();
	ТекстXML = СтрЗаменить(ТекстXML, "xmlns=""" + ПространствоИмен + """ ", "");
	
	Возврат ТекстXML;
	
КонецФункции

```