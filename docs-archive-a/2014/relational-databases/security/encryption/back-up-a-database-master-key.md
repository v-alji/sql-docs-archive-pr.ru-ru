---
title: Создание резервной копии главного ключа базы данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- database master key [SQL Server], exporting
ms.assetid: 7ad9a0a0-6e4f-4f7b-8801-8c1b9d49c4d8
author: jaszymas
ms.author: jaszymas
ms.openlocfilehash: 9a66d28fea8289719d3efb2351409e0f14379ec9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750624"
---
# <a name="back-up-a-database-master-key"></a><span data-ttu-id="536e6-102">Создание резервной копии главного ключа базы данных</span><span class="sxs-lookup"><span data-stu-id="536e6-102">Back Up a Database Master Key</span></span>
  <span data-ttu-id="536e6-103">В этом разделе описано, как выполнить резервное копирование главного ключа [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] с помощью [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="536e6-103">This topic describes how to back up a database master key in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="536e6-104">Главный ключ базы данных используется для шифрования других ключей и сертификатов внутри базы данных.</span><span class="sxs-lookup"><span data-stu-id="536e6-104">The database master key is used to encrypt other keys and certificates inside a database.</span></span> <span data-ttu-id="536e6-105">Если он удален или поврежден, то есть вероятность, что [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] не сможет расшифровать эти ключи, в результате чего зашифрованные с их помощью данные будут безвозвратно утеряны.</span><span class="sxs-lookup"><span data-stu-id="536e6-105">If it is deleted or corrupted, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] may be unable to decrypt those keys, and the data encrypted using them will be effectively lost.</span></span> <span data-ttu-id="536e6-106">По этой причине необходимо создать резервную копию главного ключа базы данных и хранить ее в надежном месте.</span><span class="sxs-lookup"><span data-stu-id="536e6-106">For this reason, you should back up the database master key and store the backup in a secure off-site location.</span></span>  
  
 <span data-ttu-id="536e6-107">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="536e6-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="536e6-108">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="536e6-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="536e6-109">Ограничения</span><span class="sxs-lookup"><span data-stu-id="536e6-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="536e6-110">Безопасность</span><span class="sxs-lookup"><span data-stu-id="536e6-110">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="536e6-111">Создание резервной копии главного ключа с помощью Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="536e6-111">To back up a database master key using Transact-SQL</span></span>](#Procedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="536e6-112">Перед началом</span><span class="sxs-lookup"><span data-stu-id="536e6-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="536e6-113">Ограничения</span><span class="sxs-lookup"><span data-stu-id="536e6-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="536e6-114">Главный ключ должен быть открыт и, таким образом, расшифрован, прежде чем производится его резервное копирование.</span><span class="sxs-lookup"><span data-stu-id="536e6-114">The master key must be open and, therefore, decrypted before it is backed up.</span></span> <span data-ttu-id="536e6-115">Если он зашифрован главным ключом службы, то его не нужно открывать явным образом.</span><span class="sxs-lookup"><span data-stu-id="536e6-115">If it is encrypted with the service master key, the master key does not have to be explicitly opened.</span></span> <span data-ttu-id="536e6-116">Но если главный ключ зашифрован только паролем, его явное открытие обязательно.</span><span class="sxs-lookup"><span data-stu-id="536e6-116">But if the master key is encrypted only with a password, it must be explicitly opened.</span></span>  
  
-   <span data-ttu-id="536e6-117">Рекомендуется создать резервную копию главного ключа сразу же после его создания и затем сохранить в надежном месте.</span><span class="sxs-lookup"><span data-stu-id="536e6-117">We recommend that you back up the master key as soon as it is created, and store the backup in a secure, off-site location.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="536e6-118">безопасность</span><span class="sxs-lookup"><span data-stu-id="536e6-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="536e6-119">Permissions</span><span class="sxs-lookup"><span data-stu-id="536e6-119">Permissions</span></span>  
 <span data-ttu-id="536e6-120">Требует разрешения CONTROL для базы данных.</span><span class="sxs-lookup"><span data-stu-id="536e6-120">Requires CONTROL permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio-with-transact-sql"></a><a name="Procedure"></a><span data-ttu-id="536e6-121">Использование SQL Server Management Studio с Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="536e6-121">Using SQL Server Management Studio with Transact-SQL</span></span>  
  
#### <a name="to-back-up-the-database-master-key"></a><span data-ttu-id="536e6-122">Создание резервной копии главного ключа базы данных</span><span class="sxs-lookup"><span data-stu-id="536e6-122">To back-up the database master key</span></span>  
  
1.  <span data-ttu-id="536e6-123">В среде [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]установите соединение с экземпляром [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , где содержится главный ключ базы данных, резервную копию которого необходимо создать.</span><span class="sxs-lookup"><span data-stu-id="536e6-123">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], connect to the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance containing the database master key you wish to back up.</span></span>  
  
2.  <span data-ttu-id="536e6-124">Выберите пароль, который будет использоваться для шифрования главного ключа базы данных на носителе данных резервной копии.</span><span class="sxs-lookup"><span data-stu-id="536e6-124">Choose a password that will be used to encrypt the database master key on the backup medium.</span></span> <span data-ttu-id="536e6-125">Пароль проходит проверку сложности.</span><span class="sxs-lookup"><span data-stu-id="536e6-125">This password is subject to complexity checks.</span></span>  
  
3.  <span data-ttu-id="536e6-126">Получите съемный носитель данных резервной копии для хранения главного ключа.</span><span class="sxs-lookup"><span data-stu-id="536e6-126">Obtain a removable backup medium for storing a copy of the backed-up key.</span></span>  
  
4.  <span data-ttu-id="536e6-127">Укажите каталог NTFS, в котором будет создана резервная копия главного ключа.</span><span class="sxs-lookup"><span data-stu-id="536e6-127">Identify an NTFS directory in which to create the backup of the key.</span></span> <span data-ttu-id="536e6-128">В этом каталоге будет сохранен файл, созданный в следующем шаге.</span><span class="sxs-lookup"><span data-stu-id="536e6-128">This is where you will create the file specified in the next step.</span></span> <span data-ttu-id="536e6-129">Он должен быть защищен с помощью списка управления доступом со строгими ограничениями.</span><span class="sxs-lookup"><span data-stu-id="536e6-129">The directory should be protected with highly restrictive access control lists (ACLs).</span></span>  
  
5.  <span data-ttu-id="536e6-130">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="536e6-130">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
6.  <span data-ttu-id="536e6-131">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="536e6-131">On the Standard bar, click **New Query**.</span></span>  
  
7.  <span data-ttu-id="536e6-132">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="536e6-132">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Creates a backup of the "AdventureWorks2012" master key. Because this master key is not encrypted by the service master key, a password must be specified when it is opened.  
    USE AdventureWorks2012;   
    GO  
    OPEN MASTER KEY DECRYPTION BY PASSWORD = 'sfj5300osdVdgwdfkli7';   
  
    BACKUP MASTER KEY TO FILE = 'c:\temp\exportedmasterkey'   
        ENCRYPTION BY PASSWORD = 'sd092735kjn$&adsg';   
    GO  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="536e6-133">Путь к файлу ключа и пароль ключа (если он существует) будет отличаться от вышеуказанного.</span><span class="sxs-lookup"><span data-stu-id="536e6-133">The file path to the key and the key's password (if it exists) will be different than what is indicated above.</span></span> <span data-ttu-id="536e6-134">Убедитесь, что оба этих параметра соответствуют настройке конкретного сервера и ключа.</span><span class="sxs-lookup"><span data-stu-id="536e6-134">Please make sure that both are specific to your server and key set-up.</span></span>  
  
8.  <span data-ttu-id="536e6-135">Скопируйте файл на носитель данных резервных копий и проверьте правильность копирования.</span><span class="sxs-lookup"><span data-stu-id="536e6-135">Copy the file to the backup medium and verify the copy.</span></span>  
  
9. <span data-ttu-id="536e6-136">Сохраните резервную копию в надежном месте вне системы.</span><span class="sxs-lookup"><span data-stu-id="536e6-136">Store the backup in a secure, off-site location.</span></span>  
  
 <span data-ttu-id="536e6-137">Дополнительные сведения см. в разделах [OPEN MASTER KEY (Transact-SQL)](/sql/t-sql/statements/open-master-key-transact-sql) и [BACKUP MASTER KEY (Transact-SQL)](/sql/t-sql/statements/backup-master-key-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="536e6-137">For more information, see [OPEN MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/open-master-key-transact-sql) and [BACKUP MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-master-key-transact-sql).</span></span>  
  
  
