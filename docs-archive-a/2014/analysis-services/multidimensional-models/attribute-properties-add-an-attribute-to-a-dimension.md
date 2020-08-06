---
title: Добавление атрибута в измерение | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- adding attributes
- automatic attribute creation
- attributes [Analysis Services], creating
- attributes [Analysis Services], adding
- manual attribute creation [Analysis Services]
ms.assetid: 25826ba1-2b38-4b34-bd3a-7eba116093ae
author: minewiskan
ms.author: owend
ms.openlocfilehash: 776591e94deedc679592cfe36d53fb1fea4093d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668474"
---
# <a name="add-an--attribute-to-a-dimension"></a>Добавление атрибута в измерение
  Атрибут можно добавить в измерение автоматически или вручную в [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .  
  
 Чтобы создать атрибут автоматически, на вкладке **Структура измерения** конструктора измерений в среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]выберите столбец, который нужно сопоставить с атрибутом, и перетащите его с панели **Представление источника данных** на панель **Атрибуты** . Служба создаст сопоставленный столбцу атрибут, которому будет присвоено имя столбца. Если атрибут с таким именем уже существует, службы [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] добавляют к имени порядковый номер, начинающийся с 1 для первого повторяющегося имени.  
  
 Чтобы создать атрибут вручную, выберите режим просмотра панели **Attributes** в виде сетки. В столбце имя в последней строке сетки щелкните **\<new attribute>** элемент. Введите имя нового атрибута. Будет создан атрибут, не сопоставленный столбцу, а всем свойствам атрибута будут присвоены значения по умолчанию. Атрибут можно сопоставить столбцу в окне **Свойства** среды [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] , настроив свойство **KeyColumns** нового атрибута.  
  
 Дополнительные сведения см. в разделах [Определение нового атрибута автоматически](attribute-properties-define-a-new-attribute-automatically.md), [Определение нового атрибута вручную](../define-a-new-attribute-manually.md), [Привязка атрибута к столбцу имени](attribute-properties-bind-an-attribute-to-a-name-column.md)и [Изменение свойства KeyColumn атрибута](attribute-properties-modify-the-keycolumn-property.md).  
  
## <a name="see-also"></a>См. также:  
 [Справочник по свойствам атрибута измерения](dimension-attribute-properties-reference.md)  
  
  
