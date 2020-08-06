---
title: Параметр конфигурации сервера "common criteria compliance enabled" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- common criteria compliance
helpviewer_keywords:
- CC (common criteria) [Database Engine]
- common criteria compliance [Database Engine]
- Risidual Information Protection [Database Engine]
- RIP (Residual Information Protection)
ms.assetid: 61766eea-c450-408d-af33-fbe7ef8c9ff2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6722d05351b8b9e80240abb4edef0633a97b6da0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655366"
---
# <a name="common-criteria-compliance-enabled-server-configuration-option"></a><span data-ttu-id="aa61d-102">Параметр конфигурации сервера «common criteria compliance enabled»</span><span class="sxs-lookup"><span data-stu-id="aa61d-102">common criteria compliance enabled Server Configuration Option</span></span>
  <span data-ttu-id="aa61d-103">Параметр common criteria compliance enabled включает следующие элементы, необходимые для поддержки стандарта Common Criteria.</span><span class="sxs-lookup"><span data-stu-id="aa61d-103">The common criteria compliance enabled option enables the following elements that are required for the Common Criteria.</span></span>  
  
|<span data-ttu-id="aa61d-104">Критерии</span><span class="sxs-lookup"><span data-stu-id="aa61d-104">Criteria</span></span>|<span data-ttu-id="aa61d-105">Описание</span><span class="sxs-lookup"><span data-stu-id="aa61d-105">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="aa61d-106">Защита остаточных данных (RIP)</span><span class="sxs-lookup"><span data-stu-id="aa61d-106">Residual Information Protection (RIP)</span></span>|<span data-ttu-id="aa61d-107">Критерий RIP требует, чтобы выделяемая память была перезаписана известным битовым шаблоном, прежде чем она будет перераспределена для другого ресурса.</span><span class="sxs-lookup"><span data-stu-id="aa61d-107">RIP requires a memory allocation to be overwritten with a known pattern of bits before memory is reallocated to a new resource.</span></span> <span data-ttu-id="aa61d-108">Соответствие стандарту RIP может повысить безопасность, однако может привести к снижению производительности.</span><span class="sxs-lookup"><span data-stu-id="aa61d-108">Meeting the RIP standard can contribute to improved security; however, overwriting the memory allocation can slow performance.</span></span> <span data-ttu-id="aa61d-109">После включения параметра common criteria compliance enabled производится перезапись памяти.</span><span class="sxs-lookup"><span data-stu-id="aa61d-109">After the common criteria compliance enabled option is enabled, the overwriting occurs.</span></span>|  
|<span data-ttu-id="aa61d-110">Возможность просматривать статистику имени входа</span><span class="sxs-lookup"><span data-stu-id="aa61d-110">The ability to view login statistics</span></span>|<span data-ttu-id="aa61d-111">После включения параметра common criteria compliance enabled включается аудит входа.</span><span class="sxs-lookup"><span data-stu-id="aa61d-111">After the common criteria compliance enabled option is enabled, login auditing is enabled.</span></span> <span data-ttu-id="aa61d-112">Каждый раз, когда пользователь успешно входит в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], становятся доступными сведения о времени последнего успешного входа, времени последней неудачной попытки входа и о количестве попыток между последним успешным уходом и текущим входом.</span><span class="sxs-lookup"><span data-stu-id="aa61d-112">Each time a user successfully logs in to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], information about the last successful login time, the last unsuccessful login time, and the number of attempts between the last successful and current login times is made available.</span></span> <span data-ttu-id="aa61d-113">Чтобы увидеть статистику входа, запросите динамическое административное представление [sys.dm_exec_sessions](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-sessions-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="aa61d-113">These login statistics can be viewed by querying the [sys.dm_exec_sessions](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-sessions-transact-sql) dynamic management view.</span></span>|  
|<span data-ttu-id="aa61d-114">Разрешение GRANT на столбец не переопределяет запрета DENY на таблицу</span><span class="sxs-lookup"><span data-stu-id="aa61d-114">That column GRANT should not override table DENY</span></span>|<span data-ttu-id="aa61d-115">После включения параметра common criteria compliance enabled запрет DENY на уровне таблицы имеет больший приоритет, чем разрешение GRANT на уровне столбца.</span><span class="sxs-lookup"><span data-stu-id="aa61d-115">After the common criteria compliance enabled option is enabled, a table-level DENY takes precedence over a column-level GRANT.</span></span> <span data-ttu-id="aa61d-116">Если этот параметр выключен, разрешение GRANT на столбец имеет больший приоритет, чем запрет DENY на уровне таблицы.</span><span class="sxs-lookup"><span data-stu-id="aa61d-116">When the option is not enabled, a column-level GRANT takes precedence over a table-level DENY.</span></span>|  
  
 <span data-ttu-id="aa61d-117">Параметр common criteria compliance enabled является дополнительным.</span><span class="sxs-lookup"><span data-stu-id="aa61d-117">The common criteria compliance enabled option is an advanced option.</span></span> <span data-ttu-id="aa61d-118">Общие условия оцениваются и сертифицируются только для выпусков Enterprise и Datacenter.</span><span class="sxs-lookup"><span data-stu-id="aa61d-118">Common criteria is only evaluated and certified for the Enterprise edition and Datacenter edition.</span></span> <span data-ttu-id="aa61d-119">Последнее состояние сертификации общих условий см. на веб-сайте [Общие условия Microsoft SQL Server](https://go.microsoft.com/fwlink/?LinkId=616319) .</span><span class="sxs-lookup"><span data-stu-id="aa61d-119">For the latest status of common criteria certification, see the [Microsoft SQL Server Common Criteria](https://go.microsoft.com/fwlink/?LinkId=616319) Web site.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="aa61d-120">Помимо включения параметра common criteria compliance enabled, необходимо загрузить и выполнить скрипт, завершающий настройку [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для соответствия стандарту Common Criteria уровня 4 (EAL4+).</span><span class="sxs-lookup"><span data-stu-id="aa61d-120">In addition to enabling the common criteria compliance enabled option, you also must download and run a script that finishes configuring [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to comply with Common Criteria Evaluation Assurance Level 4+ (EAL4+).</span></span> <span data-ttu-id="aa61d-121">Загрузить этот скрипт можно с сайта [Стандарт Common Criteria для Microsoft SQL Server](https://go.microsoft.com/fwlink/?LinkId=616319) .</span><span class="sxs-lookup"><span data-stu-id="aa61d-121">You can download this script from the [Microsoft SQL Server Common Criteria](https://go.microsoft.com/fwlink/?LinkId=616319) Web site.</span></span>  
  
 <span data-ttu-id="aa61d-122">Если для изменения значения параметра используется системная хранимая процедура sp_configure, изменить параметр common criteria compliance enabled можно только в случае, если параметр show advanced options равен 1.</span><span class="sxs-lookup"><span data-stu-id="aa61d-122">If you are using the sp_configure system stored procedure to change the setting, you can change common criteria compliance enabled only when show advanced options is set to 1.</span></span> <span data-ttu-id="aa61d-123">Установка параметра вступает в силу после перезапуска сервера.</span><span class="sxs-lookup"><span data-stu-id="aa61d-123">The setting takes effect after the server is restarted.</span></span> <span data-ttu-id="aa61d-124">Возможные значения — 0 и 1.</span><span class="sxs-lookup"><span data-stu-id="aa61d-124">The possible values are 0 and 1:</span></span>  
  
-   <span data-ttu-id="aa61d-125">Значение 0 указывает, что соответствие стандарту Common Criteria не включено.</span><span class="sxs-lookup"><span data-stu-id="aa61d-125">0 indicates that common criteria compliance is not enabled.</span></span> <span data-ttu-id="aa61d-126">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="aa61d-126">This is the default.</span></span>  
  
-   <span data-ttu-id="aa61d-127">Значение 1 указывает, что соответствие стандарту Common Criteria включено.</span><span class="sxs-lookup"><span data-stu-id="aa61d-127">1 indicates that common criteria compliance is enabled.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="aa61d-128">Примеры</span><span class="sxs-lookup"><span data-stu-id="aa61d-128">Examples</span></span>  
 <span data-ttu-id="aa61d-129">Следующий пример включает соответствие стандарту Common Criteria.</span><span class="sxs-lookup"><span data-stu-id="aa61d-129">The following example enables common criteria compliance.</span></span>  
  
```  
sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE;  
GO  
sp_configure 'common criteria compliance enabled', 1;  
GO  
RECONFIGURE  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="aa61d-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="aa61d-130">See Also</span></span>  
 [<span data-ttu-id="aa61d-131">Параметры конфигурации сервера (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="aa61d-131">Server Configuration Options &#40;SQL Server&#41;</span></span>](server-configuration-options-sql-server.md)  
  
  
