---
title: Изменение порядка параметров отчета (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: abd61e19-dba3-423c-a26c-e8bc43197d3f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ad9dd25be7a87fee089a48849fcc716e682e4c64
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737934"
---
# <a name="change-the-order-of-a-report-parameter-report-builder-and-ssrs"></a>Изменение порядка параметров отчета (построитель отчетов и службы SSRS)
  Изменять порядок параметров отчета необходимо в случае, если зависимый параметр расположен перед параметром, от которого он зависит. Порядок параметров имеет значение при наличии каскадных параметров или в случае, если необходимо показать пользователям значение по умолчанию одного параметра перед тем, как они выберут значения для других параметров. Зависимый параметр отчета ссылается (в своем запросе значений по умолчанию или в запросе допустимых значений) на параметр запроса, указывающий на параметр отчета, расположенный после него в списке параметров на панели данных отчета.  
  
 Порядок, в котором параметры отображаются на панели инструментов средства просмотра отчетов, определяется порядком параметров в области данных отчета.  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-change-the-order-of-report-parameters"></a>Изменение порядка параметров отчета  
  
1.  В области данных отчета разверните узел «Параметры».  
  
2.  Щелкните параметр и используйте кнопки со стрелками вниз и вверх, расположенные на панели инструментов области данных отчета, чтобы переместить параметр выше или ниже в списке. На рисунке показана панель инструментов области данных отчета в построителе отчетов.  
  
     ![Область данных отчета](../media/reportdatapane.png "Область данных отчета")  
  
## <a name="see-also"></a>См. также:  
 [Параметры отчета &#40;построитель отчетов и конструктор отчетов&#41;](report-parameters-report-builder-and-report-designer.md)   
 [Построитель отчетов справки по диалоговым окнам, панелям и мастерам](../report-builder-help-for-dialog-boxes-panes-and-wizards.md)   
 [Добавление каскадных параметров в построитель отчетов &#40;отчетов и SSRS&#41;](add-cascading-parameters-to-a-report-report-builder-and-ssrs.md)   
 [Учебник. Добавление параметра в отчет &#40;построитель отчетов&#41;](../tutorial-add-a-parameter-to-your-report-report-builder.md)   
 [Добавление фильтров набора данных, фильтров области данных и групповых фильтров &#40;построитель отчетов и SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md)   
 [Ссылки на коллекцию параметров (построитель отчетов и службы SSRS)](built-in-collections-parameters-collection-references-report-builder.md)  
  
  
