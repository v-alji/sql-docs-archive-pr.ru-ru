---
title: База данных распространителя | Документация Майкрософт
ms.custom: ''
ms.date: 06/30/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.configuredistributionwizard.distributiondatabase.f1
ms.assetid: 5b42a083-7a11-41d8-9e3f-320c7c907237
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d98a80be52ae77cbdaf1581a5b3397f9d11af4fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655636"
---
# <a name="distribution-database"></a><span data-ttu-id="bce68-102">База данных распространителя</span><span class="sxs-lookup"><span data-stu-id="bce68-102">Distribution Database</span></span>
  <span data-ttu-id="bce68-103">В базе данных распространителя хранятся метаданные и данные журнала для всех типов репликации, а также транзакции для репликации транзакций.</span><span class="sxs-lookup"><span data-stu-id="bce68-103">The distribution database stores metadata and history data for all types of replication, and transactions for transactional replication.</span></span>  
  
 <span data-ttu-id="bce68-104">В большинстве случаев достаточно одной базы данных распространителя.</span><span class="sxs-lookup"><span data-stu-id="bce68-104">In many cases, a single distribution database is sufficient.</span></span> <span data-ttu-id="bce68-105">Однако если несколько издателей используют один распространитель, то имеет смысл для каждого издателя создать базу данных распространителя.</span><span class="sxs-lookup"><span data-stu-id="bce68-105">However, if multiple Publishers use a single Distributor, consider creating a distribution database for each Publisher.</span></span> <span data-ttu-id="bce68-106">Это гарантирует то, что данные, проходящие через каждую базу данных распространителя, будут различаться.</span><span class="sxs-lookup"><span data-stu-id="bce68-106">Doing so ensures that the data flowing through each distribution database is distinct.</span></span> <span data-ttu-id="bce68-107">Для каждого распространителя можно указать базу данных с помощью мастера настройки распространителя.</span><span class="sxs-lookup"><span data-stu-id="bce68-107">You can specify one distribution database for the Distributor using the Configure Distribution Wizard.</span></span> <span data-ttu-id="bce68-108">При необходимости в окне **Свойства распространителя** можно указать дополнительные базы данных распространителя.</span><span class="sxs-lookup"><span data-stu-id="bce68-108">If necessary, specify additional distribution databases in the **Distributor Properties** dialog box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="bce68-109">Параметры</span><span class="sxs-lookup"><span data-stu-id="bce68-109">Options</span></span>  
 <span data-ttu-id="bce68-110">**Имя базы данных распространителя**</span><span class="sxs-lookup"><span data-stu-id="bce68-110">**Distribution database name**</span></span>  
 <span data-ttu-id="bce68-111">Введите имя базы данных распространителя.</span><span class="sxs-lookup"><span data-stu-id="bce68-111">Enter a name for the distribution database.</span></span> <span data-ttu-id="bce68-112">По умолчанию, для базы данных распространителя задано имя «distribution».</span><span class="sxs-lookup"><span data-stu-id="bce68-112">The default name for the distribution database is 'distribution'.</span></span> <span data-ttu-id="bce68-113">Максимальная длина имени — 128 символов. Имя должно быть уникальным в пределах экземпляра [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], кроме того, оно должно соответствовать правилам для идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="bce68-113">If you specify a name, the name can be a maximum of 128 characters, must be unique within an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], and must conform to the rules for identifiers.</span></span> <span data-ttu-id="bce68-114">Дополнительные сведения см. в разделе [Идентификаторы баз данных](../databases/database-identifiers.md).</span><span class="sxs-lookup"><span data-stu-id="bce68-114">For more information, see [Database Identifiers](../databases/database-identifiers.md).</span></span>  
  
 <span data-ttu-id="bce68-115">**Папка для файла базы данных распространителя** и **Папка для журнала базы данных распространителя**</span><span class="sxs-lookup"><span data-stu-id="bce68-115">**Folder for the distribution database file** and **Folder for the distribution database log file**</span></span>  
 <span data-ttu-id="bce68-116">Введите путь для базы данных распространителя и файлов журналов.</span><span class="sxs-lookup"><span data-stu-id="bce68-116">Enter the path for the distribution database and log files.</span></span> <span data-ttu-id="bce68-117">Эти пути должны быть локальными по отношению к распространителю и должны начинаться с буквы диска и двоеточия (например C:).</span><span class="sxs-lookup"><span data-stu-id="bce68-117">Paths must refer to disks that are local to the Distributor and begin with a local drive letter and colon (for example, C:).</span></span> <span data-ttu-id="bce68-118">Буквы подключенных дисков и сетевые пути являются недопустимыми.</span><span class="sxs-lookup"><span data-stu-id="bce68-118">Mapped drive letters and network paths are not valid.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bce68-119">Время, которое требуется для записи транзакций, можно уменьшить (и тем самым повысить производительность репликации) путем размещения журнала базы данных распространителя на отдельном диске.</span><span class="sxs-lookup"><span data-stu-id="bce68-119">You can decrease the time it takes to write transactions and improve the performance of replication by placing the distribution database log on a separate disk drive from the distribution database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bce68-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="bce68-120">See Also</span></span>  
 <span data-ttu-id="bce68-121">[Настройка распространения](configure-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="bce68-121">[Configure Distribution](configure-distribution.md) </span></span>  
 <span data-ttu-id="bce68-122">[Настройка публикации и распространения](configure-publishing-and-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="bce68-122">[Configure Publishing and Distribution](configure-publishing-and-distribution.md) </span></span>  
 [<span data-ttu-id="bce68-123">Просмотр и изменение свойств издателя и распространителя</span><span class="sxs-lookup"><span data-stu-id="bce68-123">View and Modify Distributor and Publisher Properties</span></span>](view-and-modify-distributor-and-publisher-properties.md)  
  
  
