# Текстовый редактор

Неправильно:

* Использование дополнительной структуры хранения текста, что облегчает вставку/удаление/позиционирование, но нивелирует использование `mmap`, удваивая ипользуемую память.
	
	Возможное решение: хранить операции, произведенные с текстом, и применять их *когда-нибудь*.

* Явный обрыв текущего блока.
	
	Возможное решение: хранить также следующий, предыдущий блоки.

* При несовпадении контрольной суммы происходит выход с ошибкой, теряется иная возможность открыть файл, кроме как удалив файл с контрольной суммой.

* Строки длиннее ширины окна терминала обрезаются.
