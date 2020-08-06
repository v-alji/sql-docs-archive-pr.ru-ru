---
title: Настройка параметра конфигурации сервера "network packet size" | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- default packet size
- size [SQL Server], packets
- packets [SQL Server], size
- network packet size option
ms.assetid: 236985bf-fc4a-4a57-98f7-a71ef977fd7b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 69e5963675349bceff6a0ee022f6dc28da03db59
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732014"
---
# <a name="configure-the-network-packet-size-server-configuration-option"></a><span data-ttu-id="78bb4-102">Настройка параметра конфигурации сервера network packet size</span><span class="sxs-lookup"><span data-stu-id="78bb4-102">Configure the network packet size Server Configuration Option</span></span>
  <span data-ttu-id="78bb4-103">В этом разделе описывается настройка `network packet size` параметра конфигурации сервера в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="78bb4-103">This topic describes how to configure the `network packet size` server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="78bb4-104">`network packet size`Параметр задает размер пакета (в байтах), который используется во всей сети.</span><span class="sxs-lookup"><span data-stu-id="78bb4-104">The `network packet size` option sets the packet size (in bytes) that is used across the whole network.</span></span> <span data-ttu-id="78bb4-105">Пакеты — это фрагменты данных фиксированного размера, с помощью которых осуществляется передача запросов и ответов между клиентами и серверами.</span><span class="sxs-lookup"><span data-stu-id="78bb4-105">Packets are the fixed-size chunks of data that transfer requests and results between clients and servers.</span></span> <span data-ttu-id="78bb4-106">Размер пакетов по умолчанию составляет 4096 байт.</span><span class="sxs-lookup"><span data-stu-id="78bb4-106">The default packet size is 4,096 bytes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="78bb4-107">Не изменяйте размер пакета, если нет уверенности в том, что это повысит производительность.</span><span class="sxs-lookup"><span data-stu-id="78bb4-107">Do not change the packet size unless you are certain that it will improve performance.</span></span> <span data-ttu-id="78bb4-108">Для большинства приложений оптимальным является размер пакета, установленный по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="78bb4-108">For most applications, the default packet size is best.</span></span>  
  
 <span data-ttu-id="78bb4-109">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="78bb4-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="78bb4-110">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="78bb4-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="78bb4-111">Ограничения</span><span class="sxs-lookup"><span data-stu-id="78bb4-111">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="78bb4-112">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="78bb4-112">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="78bb4-113">Безопасность</span><span class="sxs-lookup"><span data-stu-id="78bb4-113">Security</span></span>](#Security)  
  
-   <span data-ttu-id="78bb4-114">**Настройка параметра network packet size с помощью следующих средств:**</span><span class="sxs-lookup"><span data-stu-id="78bb4-114">**To configure the network packet size option, using:**</span></span>  
  
     [<span data-ttu-id="78bb4-115">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="78bb4-115">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="78bb4-116">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="78bb4-116">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="78bb4-117">**Дальнейшие действия.**  [После настройки параметра network packet size](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="78bb4-117">**Follow Up:**  [After you configure the network packet size option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="78bb4-118">Перед началом</span><span class="sxs-lookup"><span data-stu-id="78bb4-118">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="78bb4-119">Ограничения</span><span class="sxs-lookup"><span data-stu-id="78bb4-119">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="78bb4-120">Максимальный размер сетевого пакета для шифрованных соединений составляет 16 383 байта.</span><span class="sxs-lookup"><span data-stu-id="78bb4-120">The maximum network packet size for encrypted connections is 16,383 bytes.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="78bb4-121">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="78bb4-121">Recommendations</span></span>  
  
-   <span data-ttu-id="78bb4-122">Этот параметр является дополнительным и его следует изменять только опытным администраторам баз данных или сертифицированным техническим специалистам [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="78bb4-122">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="78bb4-123">Если приложение осуществляет массовое копирование или отправляет/получает большие объемы данных типа text или image, увеличение размера пакета может повысить эффективность работы системы за счет сокращения числа сетевых операций чтения и записи.</span><span class="sxs-lookup"><span data-stu-id="78bb4-123">If an application does bulk copy operations or sends or receives large amounts of text or image data, a packet size larger than the default might improve efficiency because it results in fewer network read-and-write operations.</span></span> <span data-ttu-id="78bb4-124">Если приложение отправляет и получает небольшие объемы информации, размер пакета можно уменьшить до 512 байт, чего в большинстве случаев достаточно.</span><span class="sxs-lookup"><span data-stu-id="78bb4-124">If an application sends and receives small amounts of information, the packet size can be set to 512 bytes, which is sufficient for most data transfers.</span></span>  
  
-   <span data-ttu-id="78bb4-125">Если система работает с несколькими сетевыми протоколами, присвойте параметру network packet size значение, оптимальное для протокола, который используется чаще всего.</span><span class="sxs-lookup"><span data-stu-id="78bb4-125">On systems that are using different network protocols, set network packet size to the size for the most common protocol used.</span></span> <span data-ttu-id="78bb4-126">Параметр network packet size позволяет повысить производительность сети, если сетевые протоколы поддерживают более крупные пакеты.</span><span class="sxs-lookup"><span data-stu-id="78bb4-126">The network packet size option improves network performance when network protocols support larger packets.</span></span> <span data-ttu-id="78bb4-127">Это значение может быть переопределено в клиентских приложениях.</span><span class="sxs-lookup"><span data-stu-id="78bb4-127">Client applications can override this value.</span></span>  
  
-   <span data-ttu-id="78bb4-128">Для запроса на изменение размера пакета также используются функции OLE DB, ODBC и DB-Library.</span><span class="sxs-lookup"><span data-stu-id="78bb4-128">You can also call OLE DB, Open Database Connectivity (ODBC), and DB-Library functions request a change the packet size.</span></span> <span data-ttu-id="78bb4-129">Если сервер не поддерживает запрошенный размер пакета, компонент [!INCLUDE[ssDE](../../includes/ssde-md.md)] отправляет клиенту предупреждающее сообщение.</span><span class="sxs-lookup"><span data-stu-id="78bb4-129">If the server cannot support the requested packet size, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] will send a warning message to the client.</span></span> <span data-ttu-id="78bb4-130">В некоторых ситуациях изменение размера пакета может привести к ошибке в канале связи, например следующей:</span><span class="sxs-lookup"><span data-stu-id="78bb4-130">In some circumstances, changing the packet size might lead to a communication link failure, such as the following:</span></span>  
  
     `Native Error: 233, no process is on the other end of the pipe.`  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="78bb4-131">безопасность</span><span class="sxs-lookup"><span data-stu-id="78bb4-131">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="78bb4-132">Permissions</span><span class="sxs-lookup"><span data-stu-id="78bb4-132">Permissions</span></span>  
 <span data-ttu-id="78bb4-133">Разрешения на выполнение хранимой процедуры **sp_configure** без параметров или только с первым параметром по умолчанию предоставляются всем пользователям.</span><span class="sxs-lookup"><span data-stu-id="78bb4-133">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="78bb4-134">Для выполнения процедуры **sp_configure** с обоими параметрами для изменения параметра конфигурации или запуска инструкции RECONFIGURE необходимо иметь разрешение ALTER SETTINGS на уровне сервера.</span><span class="sxs-lookup"><span data-stu-id="78bb4-134">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="78bb4-135">Разрешение ALTER SETTINGS неявным образом предоставлено предопределенным ролям сервера **sysadmin** и **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="78bb4-135">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="78bb4-136">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="78bb4-136">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-network-packet-size-option"></a><span data-ttu-id="78bb4-137">Настройка параметра network packet size</span><span class="sxs-lookup"><span data-stu-id="78bb4-137">To configure the network packet size option</span></span>  
  
1.  <span data-ttu-id="78bb4-138">В обозревателе объектов щелкните правой кнопкой мыши сервер и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="78bb4-138">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="78bb4-139">Щелкните узел **Дополнительно** .</span><span class="sxs-lookup"><span data-stu-id="78bb4-139">Click the **Advanced** node.</span></span>  
  
3.  <span data-ttu-id="78bb4-140">На вкладке **Сеть**выберите значение в поле **Размер сетевого пакета** .</span><span class="sxs-lookup"><span data-stu-id="78bb4-140">Under **Network**, select a value for the **Network Packet Size** box.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="78bb4-141">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="78bb4-141">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-network-packet-size-option"></a><span data-ttu-id="78bb4-142">Настройка параметра network packet size</span><span class="sxs-lookup"><span data-stu-id="78bb4-142">To configure the network packet size option</span></span>  
  
1.  <span data-ttu-id="78bb4-143">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="78bb4-143">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="78bb4-144">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="78bb4-144">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="78bb4-145">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="78bb4-145">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="78bb4-146">В этом примере описывается использование хранимой процедуры [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) для задания значения параметра `network packet size` равным `6500` байт.</span><span class="sxs-lookup"><span data-stu-id="78bb4-146">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `network packet size` option to `6500` bytes.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE ;  
GO  
EXEC sp_configure 'network packet size', 6500 ;  
GO  
RECONFIGURE;  
GO  
  
```  
  
 <span data-ttu-id="78bb4-147">Дополнительные сведения см. в разделе [Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="78bb4-147">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-network-packet-size-option"></a><a name="FollowUp"></a> <span data-ttu-id="78bb4-148">Дальнейшие действия. После настройки параметра network packet size</span><span class="sxs-lookup"><span data-stu-id="78bb4-148">Follow Up: After you configure the network packet size option</span></span>  
 <span data-ttu-id="78bb4-149">Параметр вступает в силу немедленно, без перезапуска сервера.</span><span class="sxs-lookup"><span data-stu-id="78bb4-149">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78bb4-150">См. также:</span><span class="sxs-lookup"><span data-stu-id="78bb4-150">See Also</span></span>  
 <span data-ttu-id="78bb4-151">[RECONFIGURE (Transact-SQL)](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="78bb4-151">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="78bb4-152">[Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="78bb4-152">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="78bb4-153">sp_configure (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="78bb4-153">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
