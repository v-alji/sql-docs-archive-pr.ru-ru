---
title: Восстановление главного ключа службы | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- service master key [SQL Server], importing
- service master key [SQL Server], restoring
ms.assetid: 14bdbbbe-d384-4692-b670-4243d2466fe1
author: jaszymas
ms.author: jaszymas
ms.openlocfilehash: 2ad99fc9baa518d50678ddd6e6db1ec554658823
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752064"
---
# <a name="restore-the-service-master-key"></a><span data-ttu-id="b7738-102">Восстановление главного ключа службы</span><span class="sxs-lookup"><span data-stu-id="b7738-102">Restore the Service Master Key</span></span>
  <span data-ttu-id="b7738-103">В этом разделе описывается, как восстановить главный ключ службы [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] при помощи [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b7738-103">This topic describes how to restore the service master key in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="b7738-104">Маловероятно, что когда-нибудь потребуется восстановление главного ключа службы,</span><span class="sxs-lookup"><span data-stu-id="b7738-104">It is unlikely that you will ever need to restore the service master key.</span></span> <span data-ttu-id="b7738-105">Но если все же придется это делать, эту операцию следует выполнять предельно внимательно.</span><span class="sxs-lookup"><span data-stu-id="b7738-105">If you do, you should proceed with extreme caution.</span></span> <span data-ttu-id="b7738-106">Дополнительные сведения см. в статье [Back Up the Service Master Key](service-master-key.md).</span><span class="sxs-lookup"><span data-stu-id="b7738-106">For more information, see [Back Up the Service Master Key](service-master-key.md).</span></span>  
  
 <span data-ttu-id="b7738-107">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="b7738-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="b7738-108">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="b7738-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="b7738-109">Ограничения</span><span class="sxs-lookup"><span data-stu-id="b7738-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="b7738-110">Безопасность</span><span class="sxs-lookup"><span data-stu-id="b7738-110">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="b7738-111">Восстановление главного ключа службы с помощью Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b7738-111">To restore the service master key using Transact-SQL</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b7738-112">Перед началом</span><span class="sxs-lookup"><span data-stu-id="b7738-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="b7738-113">Ограничения</span><span class="sxs-lookup"><span data-stu-id="b7738-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="b7738-114">При восстановлении главного ключа службы [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] расшифровывает все ключи и секретные коды, зашифрованные вместе с текущим главным ключом службы, а затем зашифровывает их вместе с восстановленным ключом из файла резервной копии.</span><span class="sxs-lookup"><span data-stu-id="b7738-114">When the service master key is restored, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] decrypts all the keys and secrets that have been encrypted with the current service master key, and then encrypts them with the service master key loaded from the backup file.</span></span>  
  
-   <span data-ttu-id="b7738-115">Если во время расшифровки любого объекта произойдет ошибка, восстановление будет прервано.</span><span class="sxs-lookup"><span data-stu-id="b7738-115">If any one of the decryptions fails, the restore will fail.</span></span> <span data-ttu-id="b7738-116">Чтобы пропускать ошибки, можно использовать параметр FORCE, но это приведет к потере всех данных, которые не удается расшифровать.</span><span class="sxs-lookup"><span data-stu-id="b7738-116">You can use the FORCE option to ignore errors, but this option will cause the loss of any data that cannot be decrypted.</span></span>  
  
-   <span data-ttu-id="b7738-117">Повторное формирование иерархии шифрования — ресурсоемкая операция.</span><span class="sxs-lookup"><span data-stu-id="b7738-117">Regenerating the encryption hierarchy is a resource-intensive operation.</span></span> <span data-ttu-id="b7738-118">Ее нужно назначить на период низкой нагрузки на сервер.</span><span class="sxs-lookup"><span data-stu-id="b7738-118">You should schedule this during a period of low demand.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="b7738-119">Главный ключ службы является корнем иерархии шифрования [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b7738-119">The service master key is the root of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] encryption hierarchy.</span></span> <span data-ttu-id="b7738-120">Этот ключ явно или неявно защищает все остальные ключи в дереве.</span><span class="sxs-lookup"><span data-stu-id="b7738-120">The service master key directly or indirectly secures all other keys in the tree.</span></span> <span data-ttu-id="b7738-121">Если зависящий от него ключ не может быть расшифрован, но восстановление продолжено, то данные, защищенные этим ключом, будут утеряны.</span><span class="sxs-lookup"><span data-stu-id="b7738-121">If a dependent key cannot be decrypted during a forced restore, data that is secured by that key will be lost.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b7738-122">безопасность</span><span class="sxs-lookup"><span data-stu-id="b7738-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b7738-123">Permissions</span><span class="sxs-lookup"><span data-stu-id="b7738-123">Permissions</span></span>  
 <span data-ttu-id="b7738-124">Необходимо разрешение CONTROL SERVER на сервер.</span><span class="sxs-lookup"><span data-stu-id="b7738-124">Requires CONTROL SERVER permission on the server.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b7738-125">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b7738-125">Using Transact-SQL</span></span>  
  
#### <a name="to-restore-the-service-master-key"></a><span data-ttu-id="b7738-126">Восстановление главного ключа службы</span><span class="sxs-lookup"><span data-stu-id="b7738-126">To restore the service master key</span></span>  
  
1.  <span data-ttu-id="b7738-127">Сохраните резервную копию главного ключа службы с физического носителя данных резервных копий или из папки локальной файловой системы.</span><span class="sxs-lookup"><span data-stu-id="b7738-127">Retrieve a copy of the backed-up service master key, either from a physical backup medium or a directory on the local file system.</span></span>  
  
2.  <span data-ttu-id="b7738-128">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b7738-128">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
3.  <span data-ttu-id="b7738-129">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="b7738-129">On the Standard bar, click **New Query**.</span></span>  
  
4.  <span data-ttu-id="b7738-130">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="b7738-130">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Restores the service master key from a backup file.  
    RESTORE SERVICE MASTER KEY   
        FROM FILE = 'c:\temp_backups\keys\service_master_key'   
        DECRYPTION BY PASSWORD = '3dH85Hhk003GHk2597gheij4';  
    GO  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="b7738-131">Путь к файлу ключа и пароль ключа (если он существует) будет отличаться от вышеуказанного.</span><span class="sxs-lookup"><span data-stu-id="b7738-131">The file path to the key and the key's password (if it exists) will be different than what is indicated above.</span></span> <span data-ttu-id="b7738-132">Убедитесь, что оба этих параметра соответствуют настройке конкретного сервера и ключа.</span><span class="sxs-lookup"><span data-stu-id="b7738-132">Please make sure that both are specific to your server and key set-up.</span></span>  
  
  
