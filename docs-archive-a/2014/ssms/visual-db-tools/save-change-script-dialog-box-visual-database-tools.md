---
title: Диалоговое окно "Сохранить скрипт изменений" (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.dlgbox.generatechangescript
- vdtsql.chm:65544
ms.assetid: fc9d1639-5efa-44fe-a04f-4d4d0def2833
author: stevestein
ms.author: sstein
ms.openlocfilehash: 19a2bb2ce9a219c195421e2efa203fc115e1ae1b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727725"
---
# <a name="save-change-script-dialog-box-visual-database-tools"></a><span data-ttu-id="28331-102">Диалоговое окно "Сохранить скрипт изменений" (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="28331-102">Save Change Script Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="28331-103">Это диалоговое окно показывает скрипт [!INCLUDE[tsql](../../includes/tsql-md.md)] изменений, сделанных со времени последнего сохранения таблицы.</span><span class="sxs-lookup"><span data-stu-id="28331-103">This dialog box shows the [!INCLUDE[tsql](../../includes/tsql-md.md)] script for the changes you have made since you last saved the table.</span></span> <span data-ttu-id="28331-104">Оно также позволяет сохранить скрипт в текстовом файле в выбранном местоположении.</span><span class="sxs-lookup"><span data-stu-id="28331-104">It also allows you to save the script to a text file at a location you choose.</span></span>  
  
 <span data-ttu-id="28331-105">Открыть это диалоговое окно также можно после совершения несохраненных изменений таблицы в конструкторе таблиц.</span><span class="sxs-lookup"><span data-stu-id="28331-105">You can access this dialog box after you have made unsaved changes to a table in Table Designer.</span></span> <span data-ttu-id="28331-106">В меню **Конструктор таблиц** выберите пункт **Создать скрипт изменения**.</span><span class="sxs-lookup"><span data-stu-id="28331-106">On the **Table Designer** menu, click **Generate Change Script**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="28331-107">Скрипты изменений, содержащиеся в визуальных инструментах для баз данных, не содержат средств обработки ошибок.</span><span class="sxs-lookup"><span data-stu-id="28331-107">Change scripts provided by Visual Database Tools contain no error handling.</span></span> <span data-ttu-id="28331-108">Они предполагают, что объекты базы данных не изменились с момента открытия инструментального средства; поэтому возникновение проблем, связанных с изменением объектов, невозможно.</span><span class="sxs-lookup"><span data-stu-id="28331-108">They assume that database objects have not changed since the tool was opened, and that change-related problems will therefore not occur.</span></span> <span data-ttu-id="28331-109">Перед выполнением скрипта изменений следует включить соответствующие инструкции обработки ошибок.</span><span class="sxs-lookup"><span data-stu-id="28331-109">Before running a change script, you should include the appropriate error-handling statements.</span></span>  
  
## <a name="options"></a><span data-ttu-id="28331-110">Параметры</span><span class="sxs-lookup"><span data-stu-id="28331-110">Options</span></span>  
 <span data-ttu-id="28331-111">**Автоматически создавать скрипт изменений при каждом сохранении**</span><span class="sxs-lookup"><span data-stu-id="28331-111">**Automatically generate change script on every save**</span></span>  
 <span data-ttu-id="28331-112">Если флажок установлен, то диалоговое окно **Сохранить скрипт изменений** будет выводиться каждый раз при сохранении изменений таблицы.</span><span class="sxs-lookup"><span data-stu-id="28331-112">If checked, the **Save Change Script** dialog box will appear any time you save changes to a table.</span></span>  
  
 <span data-ttu-id="28331-113">**Да**</span><span class="sxs-lookup"><span data-stu-id="28331-113">**Yes**</span></span>  
 <span data-ttu-id="28331-114">Разверните диалоговое окно **Сохранить** , где можно выбрать местоположение текстового файла.</span><span class="sxs-lookup"><span data-stu-id="28331-114">Bring up the **Save** dialog box where you can choose the location for the text file.</span></span>  
  
 <span data-ttu-id="28331-115">**Нет**</span><span class="sxs-lookup"><span data-stu-id="28331-115">**No**</span></span>  
 <span data-ttu-id="28331-116">Отменить создание скрипта изменения.</span><span class="sxs-lookup"><span data-stu-id="28331-116">Cancel the creation of the change script.</span></span>  
  
  
