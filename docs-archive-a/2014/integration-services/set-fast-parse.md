---
title: Задать быстрый синтаксический анализ | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: dcd1dc09-6eaf-440b-9ce6-fef779ff794f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e6ff2c6ecd536dd5ecc34dceb358ffcf578ff3a7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654409"
---
# <a name="set-fast-parse"></a><span data-ttu-id="757a1-102">Установка быстрого анализа</span><span class="sxs-lookup"><span data-stu-id="757a1-102">Set Fast Parse</span></span>
  <span data-ttu-id="757a1-103">Свойство быстрого анализа необходимо установить для каждого столбца источника или преобразования, использующего этот анализ.</span><span class="sxs-lookup"><span data-stu-id="757a1-103">The fast parse property must be set for each column of the source or transformation that uses fast parse.</span></span> <span data-ttu-id="757a1-104">Для установки этого свойства используется расширенный редактор источника «Неструктурированный файл» и преобразование «Преобразование данных».</span><span class="sxs-lookup"><span data-stu-id="757a1-104">To set the property, use the Advanced editor of the Flat File source and Data Conversion transformation.</span></span>  
  
### <a name="to-set-fast-parse"></a><span data-ttu-id="757a1-105">Установка быстрого анализа</span><span class="sxs-lookup"><span data-stu-id="757a1-105">To set fast parse</span></span>  
  
1.  <span data-ttu-id="757a1-106">Щелкните правой кнопкой источник "Неструктурированный файл" или преобразование "Преобразование данных" и выберите **Показать расширенный редактор**.</span><span class="sxs-lookup"><span data-stu-id="757a1-106">Right-click the Flat File source or Data Conversion transformation, and then click **Show Advanced Editor**.</span></span>  
  
2.  <span data-ttu-id="757a1-107">В диалоговом окне **Расширенный редактор** перейдите на вкладку **Свойства входов и выходов** .</span><span class="sxs-lookup"><span data-stu-id="757a1-107">In the **Advanced Editor** dialog box, click the **Input and Output Properties** tab.</span></span>  
  
3.  <span data-ttu-id="757a1-108">На панели **Входы и выходы** щелкните столбец, для которого нужно включить быстрый анализ.</span><span class="sxs-lookup"><span data-stu-id="757a1-108">In the **Inputs and Outputs** pane, click the column for which you want to enable fast parse.</span></span>  
  
4.  <span data-ttu-id="757a1-109">В окно свойств разверните узел **пользовательские свойства** и задайте `FastParse` для свойства значение `True` .</span><span class="sxs-lookup"><span data-stu-id="757a1-109">In the Properties window, expand the **Custom Properties** node, and then set the `FastParse` property to `True`.</span></span>  
  
5.  <span data-ttu-id="757a1-110">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="757a1-110">Click **OK**.</span></span>  
  
  
