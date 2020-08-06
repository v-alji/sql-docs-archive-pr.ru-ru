---
title: Преобразование "Сортировка" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.sorttrans.f1
helpviewer_keywords:
- Sort transformation
- descending sorts
- ascending sorts
- sorting data [Integration Services]
- multiple sorts
- duplicate data [Integration Services]
ms.assetid: 728c9351-84a8-4a89-be4d-d50d4adc04e0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7039d02b6cc55355c3b27e5694474df4666570ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665451"
---
# <a name="sort-transformation"></a>преобразование «Сортировка»
  Это преобразование сортирует входные данные по возрастанию или убыванию и копирует отсортированные данные на выход преобразования. К входным данным можно применять несколько сортировок, при этом каждая сортировка будет иметь свой номер, определяющий ее последовательность. Данные будут сначала упорядочены по столбцу с наименьшим номером, затем по столбцу со следующим наименьшим номером и т. д. Например, если у столбца **Страна** номер сортировки 1, а у столбца **Город** номер сортировки 2, выходные данные будут отсортированы сначала по названиям стран, а затем по названиям городов. Положительный номер сортировки означает, что данные будут упорядочены по возрастанию, а отрицательный — по убыванию. У столбцов, по которым сортировка производиться не будет, номер сортировки равен 0. Такие столбцы автоматически копируются на выход преобразования вместе с отсортированными столбцами.  
  
 Преобразование «Сортировка» включает набор параметров сравнения, согласно которым будут обрабатываться данные в столбце. Дополнительные сведения см. в статье [Comparing String Data](../comparing-string-data.md).  
  
> [!NOTE]  
>  Преобразование «Сортировка» не сортирует идентификаторы GUID в том же порядке, что и предложение ORDER BY языка Transact-SQL. Преобразование «Сортировка» сортирует идентификаторы GUID, начинающиеся с символов с 0 по 9, перед идентификаторами GUID, начинающимися с символов с A по F, а предложение ORDER BY в реализации [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)]выполняет сортировку наоборот. Дополнительные сведения см. в разделе [Предложение ORDER BY (Transact-SQL)](/sql/t-sql/queries/select-order-by-clause-transact-sql).  
  
 В процессе сортировки это преобразование может удалять повторяющиеся строки. Повторяющимися являются строки с одинаковым значением ключа сортировки. Значение ключа сортировки формируется на основе использующихся параметров сравнения строк, то есть у разных строковых литералов могут быть одинаковые значения ключа сортировки. Строки во входных столбцах с разными значениями, но одинаковыми ключами сортировки определяются преобразованием как повторяющиеся.  
  
 Преобразование «Сортировка» включает пользовательское свойство `MaximumThreads`, которое может быть обновлено выражением свойства при загрузке пакета. Дополнительные сведения см. в разделах [Выражения служб Integration Services (SSIS)](../../expressions/integration-services-ssis-expressions.md), [Использование выражений свойств в пакетах](../../expressions/use-property-expressions-in-packages.md) и [Пользовательские свойства преобразований](transformation-custom-properties.md).  
  
 Это преобразование имеет один вход и один выход. Оно не поддерживает выход ошибок.  
  
## <a name="configuration-of-the-sort-transformation"></a>Настройка преобразования «Сортировка»  
 Свойства могут устанавливаться через конструктор служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)] или с помощью программных средств.  
  
 Сведения о свойствах, которые можно установить в диалоговом окне **Редактор преобразования «Сортировка»** , см. в разделе [Sort Transformation Editor](../../sort-transformation-editor.md).  
  
 Диалоговое окно **Расширенный редактор** содержит свойства, которые можно установить с помощью программных средств. Дополнительные сведения о свойствах, которые вы можете задать в диалоговом окне **Расширенный редактор** или программными средствами, см. в следующих разделах.  
  
-   [Общие свойства](../../common-properties.md)  
  
-   [Пользовательские свойства преобразований](transformation-custom-properties.md)  
  
## <a name="related-tasks"></a>Связанные задачи  
 Дополнительные сведения о настройке свойств компонента см. в разделе [Установление свойств компонента потока данных](../set-the-properties-of-a-data-flow-component.md).  
  
## <a name="related-content"></a>См. также  
 Образец [Пользовательский компонент SortDeDuplicateDelimitedString служб SSIS](https://go.microsoft.com/fwlink/?LinkId=220821)на сайте codeplex.com.  
  
## <a name="see-also"></a>См. также:  
 [Поток данных](../data-flow.md)   
 [Преобразования служб Integration Services](integration-services-transformations.md)  
  
  