---
title: Привязка атрибута к столбцу имени | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- binding attributes [Analysis Services]
- name columns [Analysis Services]
- attributes [Analysis Services], binding
ms.assetid: 467f0cf3-8691-476d-a7fb-a5df4e374eaf
author: minewiskan
ms.author: owend
ms.openlocfilehash: e25c59d34744e7a067c2b3e83d248c4674772737
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667933"
---
# <a name="bind-an-attribute-to-a-name-column"></a><span data-ttu-id="7be5b-102">Привязка атрибута к столбцу имени</span><span class="sxs-lookup"><span data-stu-id="7be5b-102">Bind an Attribute to a Name Column</span></span>
  <span data-ttu-id="7be5b-103">В этой процедуре описана привязка атрибута к столбцу имени вручную с помощью панели **Атрибуты** в конструкторе измерений и с помощью диалогового окна **Привязка объектов** .</span><span class="sxs-lookup"><span data-stu-id="7be5b-103">This procedure describes how to bind an attribute to a name column manually by using the **Attributes** pane in the Dimension Designer and by using the **Object Binding** dialog box.</span></span>  
  
### <a name="to-bind-an-attribute-to-a-name-column"></a><span data-ttu-id="7be5b-104">Привязка атрибута к столбцу имени</span><span class="sxs-lookup"><span data-stu-id="7be5b-104">To bind an attribute to a name column</span></span>  
  
1.  <span data-ttu-id="7be5b-105">В конструкторе измерений откройте измерение, в котором необходимо создать атрибут.</span><span class="sxs-lookup"><span data-stu-id="7be5b-105">In Dimension Designer, open the dimension in which you want to create the attribute.</span></span>  
  
2.  <span data-ttu-id="7be5b-106">На панели **Атрибуты** на вкладке **Структура измерения** щелкните правой кнопкой мыши атрибут, который нужно настроить, а затем щелкните **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="7be5b-106">On the **Dimension Structure** tab, in the **Attributes** pane, right-click the attribute that you want to configure, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="7be5b-107">В окне **Свойства** найдите свойство **NameColumn** , а затем выберите **(новое)**.</span><span class="sxs-lookup"><span data-stu-id="7be5b-107">In the **Properties** window, locate the **NameColumn** property, and then select **(new)**.</span></span>  
  
4.  <span data-ttu-id="7be5b-108">В диалоговом окне **Привязка объекта** в качестве значения **Тип привязки**выберите **Привязка к столбцу**.</span><span class="sxs-lookup"><span data-stu-id="7be5b-108">In the **Object Binding** dialog box, for **Binding type**, select **Column binding**.</span></span>  
  
5.  <span data-ttu-id="7be5b-109">В списке **Исходный столбец** выберите столбец, к которому будет привязан атрибут, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="7be5b-109">In the **Source column** list, select the column to which the attribute will be bound, and then click **OK**.</span></span>  
  
  
