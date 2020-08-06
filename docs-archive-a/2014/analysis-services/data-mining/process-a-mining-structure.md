---
title: Обработка структуры интеллектуального анализа данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining structures [Analysis Services], processing
ms.assetid: 4162f33e-c23f-4293-8905-271781e45fa4
author: minewiskan
ms.author: owend
ms.openlocfilehash: 76d25a927ae61ee5ffadf4ca21073a1c04cdb542
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734614"
---
# <a name="process-a-mining-structure"></a>обработать структуру интеллектуального анализа данных
  Перед тем как получить возможность просмотра или работы с моделями интеллектуального анализа данных, связанными со структурой интеллектуального анализа данных, необходимо развернуть проект служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] и обработать структуру интеллектуального анализа данных, а также модель интеллектуального анализа данных. Также при внесении изменений в структуру интеллектуального анализа данных или модель интеллектуального анализа данных будет выдано приглашение к их повторному развертыванию и обработке. При обработке структуры на вкладке **Структура интеллектуального анализа данных** конструктора интеллектуального анализа данных в среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] обрабатываются все связанные с ней модели.  
  
 Обработка структуры интеллектуального анализа данных производится с помощью следующих средств.  
  
-   [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]  
  
-   XMLA: команда Process  
  
 Дополнительные сведения об обработке отдельных моделей см. в разделе [Обработка модели интеллектуального анализа данных](process-a-mining-model.md).  
  
### <a name="to-process-a-mining-structure-and-all-associated-mining-models-using-sql-server-data-tools"></a>Обработка структуры интеллектуального анализа данных и всех связанных с ней моделей интеллектуального анализа данных с помощью SQL Server Data Tools  
  
1.  Выберите пункт **Обработать структуру интеллектуального анализа данных и все модели** из пункта меню **Модель интеллектуального анализа данных** в среде [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].  
  
     При внесении изменений в структуру будет выдано приглашение к повторному развертыванию структуры перед обработкой моделей. Нажмите кнопку **Да**.  
  
2.  В диалоговом окне **Обработка \<structure> структуры интеллектуального анализа данных** нажмите кнопку **выполнить** .  
  
     Откроется диалоговое окно **Ход обработки** , отображающее подробные сведения об обработке модели.  
  
3.  Нажмите кнопку **Закрыть** в диалоговом окне **Ход обработки** после завершения обработки моделей.  
  
4.  В диалоговом окне **Обработка \<structure> структуры интеллектуального анализа данных** нажмите кнопку **Закрыть** .  
  
## <a name="see-also"></a>См. также:  
 [Задачи и инструкции по структуре интеллектуального анализа данных](mining-structure-tasks-and-how-tos.md)  
  
  