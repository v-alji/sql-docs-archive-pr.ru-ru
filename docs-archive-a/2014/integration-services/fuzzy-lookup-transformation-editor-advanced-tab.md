---
title: Редактор преобразования "Нечеткий уточняющий запрос" (вкладка "Дополнительно") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.fuzzylookuptransformation.advanced.f1
helpviewer_keywords:
- Fuzzy Lookup Transformation Editor
ms.assetid: 0a2919be-2ea7-4c06-82b8-0ffad5f0dd83
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 68f53eb2735dc07656fc8ff2b81c3259caa4847b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729630"
---
# <a name="fuzzy-lookup-transformation-editor-advanced-tab"></a>Редактор преобразования «Нечеткий уточняющий запрос» (вкладка «Дополнительно»)
  Вкладка **Дополнительно** диалогового окна **Редактор преобразования «Нечеткий уточняющий запрос»** позволяет задать параметры нечеткого поиска.  
  
 Дополнительные сведения о преобразовании «Нечеткий уточняющий запрос» см. в разделе [Fuzzy Lookup Transformation](data-flow/transformations/lookup-transformation.md).  
  
## <a name="options"></a>Варианты  
 **Максимальное количество совпадений, которое следует выводить на каждый уточняющий запрос**  
 Указывает максимальное число совпадений, возвращаемое преобразованием для каждой входной строки. Значение по умолчанию — **1**.  
  
 **Порог подобия**  
 Задает порог подобия на уровне компонента при помощи данного ползунка. Чем ближе значение к 1, тем ближе к искомому должно быть значение строки уточняющего запроса. Увеличение порогового значения может увеличить скорость соответствия, так как при этом будет рассматриваться меньшее количество предполагаемых совпадений.  
  
 **Разделители токенов**  
 Определяет разделители, используемые преобразованием для разделения значений столбца.  
  
## <a name="see-also"></a>См. также:  
 [Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md)   
 [Редактор преобразования "Нечеткий уточняющий запрос" &#40;вкладка "ссылочная таблица"&#41;](../../2014/integration-services/fuzzy-lookup-transformation-editor-reference-table-tab.md)   
 [Редактор преобразования "Нечеткий уточняющий запрос" (вкладка "Столбцы")](../../2014/integration-services/fuzzy-lookup-transformation-editor-columns-tab.md)  
  
  
