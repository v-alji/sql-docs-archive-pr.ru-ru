---
title: Настройка срока хранения журнала (SQL Server Management Studio) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- history retention periods [SQL Server replication]
- retention periods [SQL Server replication]
ms.assetid: c288daab-5181-4d4b-ba2a-8a147098e758
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 13dcf2ad9a9d619a7fdef9c1ed3f7b970e420cdd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668766"
---
# <a name="set-the-history-retention-period-sql-server-management-studio"></a><span data-ttu-id="33f74-102">настроить срок хранения журнала (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="33f74-102">Set the History Retention Period (SQL Server Management Studio)</span></span>
  <span data-ttu-id="33f74-103">Укажите срок хранения журнала на странице **Общие** диалогового окна **Свойства базы данных распространителя — \<DistributionDatabase>** .</span><span class="sxs-lookup"><span data-stu-id="33f74-103">Specify the history retention period on the **General** page of the **Distribution Database Properties - \<DistributionDatabase>** dialog box.</span></span> <span data-ttu-id="33f74-104">Эта настройка управляет длительностью хранения журнала агента репликации.</span><span class="sxs-lookup"><span data-stu-id="33f74-104">This setting controls how long replication agent history is stored.</span></span> <span data-ttu-id="33f74-105">Эту страницу можно открыть на странице **Общие** диалогового окна **Свойства распространителя — \<Distributor>** .</span><span class="sxs-lookup"><span data-stu-id="33f74-105">This page is available from the **General** page of the **Distributor Properties - \<Distributor>** dialog box.</span></span> <span data-ttu-id="33f74-106">Дополнительные сведения о доступе к этому диалоговому окну см. в статье [Просмотр и изменение свойств издателя и распространителя](view-and-modify-distributor-and-publisher-properties.md).</span><span class="sxs-lookup"><span data-stu-id="33f74-106">For more information about accessing this dialog box, see [View and Modify Distributor and Publisher Properties](view-and-modify-distributor-and-publisher-properties.md).</span></span>  
  
### <a name="to-specify-the-history-retention-period"></a><span data-ttu-id="33f74-107">Указание срока хранения журнала</span><span class="sxs-lookup"><span data-stu-id="33f74-107">To specify the history retention period</span></span>  
  
1.  <span data-ttu-id="33f74-108">На странице **Общие** диалогового окна **Свойства распространителя — \<Distributor>** нажмите кнопку свойств ( **...** ) для базы данных распространителя.</span><span class="sxs-lookup"><span data-stu-id="33f74-108">On the **General** page of the **Distributor Properties - \<Distributor>** dialog box, click the properties button (**...**) for the distribution database.</span></span>  
  
2.  <span data-ttu-id="33f74-109">Введите значение в поле **Сохранять журнал производительности репликации не менее** .</span><span class="sxs-lookup"><span data-stu-id="33f74-109">Enter a value in the **Store replication performance history at least** box.</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="33f74-110">См. также:</span><span class="sxs-lookup"><span data-stu-id="33f74-110">See Also</span></span>  
 [<span data-ttu-id="33f74-111">Настройка распространения</span><span class="sxs-lookup"><span data-stu-id="33f74-111">Configure Distribution</span></span>](configure-distribution.md)  
  
  
