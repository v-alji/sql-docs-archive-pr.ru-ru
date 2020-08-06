---
title: Соединение с сервером Oracle (страница "Свойства соединения") | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.oracleconnection.connectionprops.f1
helpviewer_keywords:
- Connect to Server dialog box, replication
ms.assetid: 1bb7396f-cbb2-4f88-b82b-543287ed4172
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4c76a3058283a098357701a44de48efff917acd7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655089"
---
# <a name="connect-to-server-oracle-connection-properties"></a><span data-ttu-id="b9de8-102">Соединение с сервером (Oracle), свойства соединения</span><span class="sxs-lookup"><span data-stu-id="b9de8-102">Connect to Server (Oracle), Connection Properties</span></span>
  <span data-ttu-id="b9de8-103">Вкладка **Свойства соединения** диалогового окна **Соединение с сервером** позволяет задать параметры публикации **Шлюз** или **Полный**.</span><span class="sxs-lookup"><span data-stu-id="b9de8-103">Use the **Connection Properties** tab of the **Connect to Server** dialog box to specify a publishing option of **Gateway** or **Complete**.</span></span> <span data-ttu-id="b9de8-104">После идентификации издателя изменить данный параметр без удаления и перенастройки издателя невозможно.</span><span class="sxs-lookup"><span data-stu-id="b9de8-104">After a Publisher is identified, this option cannot be changed without dropping and reconfiguring the Publisher.</span></span> <span data-ttu-id="b9de8-105">Дополнительные сведения см. в статье [Настройка издателя Oracle](non-sql/configure-an-oracle-publisher.md).</span><span class="sxs-lookup"><span data-stu-id="b9de8-105">For more information, see [Configure an Oracle Publisher](non-sql/configure-an-oracle-publisher.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="b9de8-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="b9de8-106">Options</span></span>  
 <span data-ttu-id="b9de8-107">**Тип издателя**</span><span class="sxs-lookup"><span data-stu-id="b9de8-107">**Publisher type**</span></span>  
 <span data-ttu-id="b9de8-108">Выберите **Шлюз** или **Полный**.</span><span class="sxs-lookup"><span data-stu-id="b9de8-108">Select **Gateway** or **Complete**.</span></span> <span data-ttu-id="b9de8-109">Параметр **Полный** обеспечивает публикации моментальных снимков и транзакций полным набором поддерживаемых функций, необходимых для публикаций Oracle.</span><span class="sxs-lookup"><span data-stu-id="b9de8-109">The **Complete** option is designed to provide snapshot and transactional publications with the complete set of supported features for Oracle publishing.</span></span> <span data-ttu-id="b9de8-110">Параметр **Шлюз** оптимизирует работу системы для случаев, когда шлюзом между системами выступает репликация.</span><span class="sxs-lookup"><span data-stu-id="b9de8-110">The **Gateway** option provides specific design optimizations to improve performance for cases where replication serves as a gateway between systems.</span></span> <span data-ttu-id="b9de8-111">Параметр **Шлюз** нельзя использовать, если одна и та же таблица будет публиковаться в нескольких публикациях транзакций.</span><span class="sxs-lookup"><span data-stu-id="b9de8-111">The **Gateway** option cannot be used if you plan to publish the same table in multiple transactional publications.</span></span> <span data-ttu-id="b9de8-112">Если выбран параметр **Шлюз**, то таблица может использоваться только в одной публикации транзакций и в любом количестве публикаций моментальных снимков.</span><span class="sxs-lookup"><span data-stu-id="b9de8-112">A table can appear in at most one transactional publication and any number of snapshot publications if you select **Gateway**.</span></span>  
  
 <span data-ttu-id="b9de8-113">**Время ожидания**</span><span class="sxs-lookup"><span data-stu-id="b9de8-113">**Timeouts**</span></span>  
 <span data-ttu-id="b9de8-114">Указывает, как долго распространитель [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] должен пытаться подключиться к издателю Oracle, прежде чем выдать ошибку времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="b9de8-114">Specify how long the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributor should attempt to connect to the Oracle Publisher before a timeout error occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9de8-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="b9de8-115">See Also</span></span>  
 <span data-ttu-id="b9de8-116">[Глоссарий терминов по публикации Oracle](non-sql/glossary-of-terms-for-oracle-publishing.md) </span><span class="sxs-lookup"><span data-stu-id="b9de8-116">[Glossary of Terms for Oracle Publishing](non-sql/glossary-of-terms-for-oracle-publishing.md) </span></span>  
 [<span data-ttu-id="b9de8-117">Настройка производительности для издателей Oracle</span><span class="sxs-lookup"><span data-stu-id="b9de8-117">Performance Tuning for Oracle Publishers</span></span>](non-sql/performance-tuning-for-oracle-publishers.md)  
  
  
