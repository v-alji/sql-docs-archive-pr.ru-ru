---
title: Создание экземпляров зеркальных таблиц и отслеживание CDC | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- mirTab
ms.assetid: 260c1617-eecc-4007-a84d-3c5778ce46b6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 78daea310112cf7e9e78e489097fe9a76e69996b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728622"
---
# <a name="generate-mirror-tables-and-cdc-capture-instances"></a><span data-ttu-id="a74a9-102">Создание экземпляров зеркальных таблиц и отслеживание CDC</span><span class="sxs-lookup"><span data-stu-id="a74a9-102">Generate Mirror Tables and CDC Capture Instances</span></span>
  <span data-ttu-id="a74a9-103">Страница формирования зеркальных таблиц используется для создания зеркальных таблиц для таблиц, включенных в экземпляр CDC.</span><span class="sxs-lookup"><span data-stu-id="a74a9-103">Use the Generate Mirror Tables page to generate the mirror tables for the tables you included in the CDC instance</span></span>  
  
 <span data-ttu-id="a74a9-104">Нажмите кнопку **Выполнить** , чтобы создать зеркальные таблицы.</span><span class="sxs-lookup"><span data-stu-id="a74a9-104">Click **Run** to create the mirror tables.</span></span> <span data-ttu-id="a74a9-105">Процесс создания каждой таблицы отображается на экране, а по его окончании выдается сообщение, в котором говорится, была ли таблица создана успешно.</span><span class="sxs-lookup"><span data-stu-id="a74a9-105">The progress for the creation of each table is displayed and a message is displayed to let you know whether each mirror table is completed successfully or with errors.</span></span> <span data-ttu-id="a74a9-106">Если возникли ошибки, нажмите кнопку **Сведения** , чтобы открыть диалоговое окно с описанием ошибки.</span><span class="sxs-lookup"><span data-stu-id="a74a9-106">If any errors occur, click **Details** to see a dialog box with an explanation of the error.</span></span>  
  
 <span data-ttu-id="a74a9-107">Если какую-либо таблицу создать не удалось, то можно либо продолжить выполнение, либо удалить таблицу, которую не удалось создать, а затем продолжить работу.</span><span class="sxs-lookup"><span data-stu-id="a74a9-107">If any of the tables fail to be created, you can choose to continue or delete any tables that failed before continuing.</span></span> <span data-ttu-id="a74a9-108">После завершения работы мастера можно решить, следует ли исправить таблицу в базе данных-источнике Oracle или не использовать ее в экземпляре CDC.</span><span class="sxs-lookup"><span data-stu-id="a74a9-108">After you finish running the wizard, you can decide whether to fix the table in the Oracle source database or not use it in the CDC instance.</span></span> <span data-ttu-id="a74a9-109">Если выбрано исправление таблицы, то ее можно будет добавить через [Edit Tables](edit-tables.md).</span><span class="sxs-lookup"><span data-stu-id="a74a9-109">If you fix the table, you can add it when you [Edit Tables](edit-tables.md).</span></span>  
  
 <span data-ttu-id="a74a9-110">Нажмите кнопку **Далее** , чтобы открыть страницу [Finish](finish.md) .</span><span class="sxs-lookup"><span data-stu-id="a74a9-110">Click **Next** to open the [Finish](finish.md) page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a74a9-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="a74a9-111">See Also</span></span>  
 [<span data-ttu-id="a74a9-112">Как создать экземпляр базы данных изменений SQL Server</span><span class="sxs-lookup"><span data-stu-id="a74a9-112">How to Create the SQL Server Change Database Instance</span></span>](how-to-create-the-sql-server-change-database-instance.md)  
  
  
