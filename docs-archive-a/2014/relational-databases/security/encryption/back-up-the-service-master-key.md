---
title: Создание резервной копии главного ключа службы | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- service master key [SQL Server], exporting
ms.assetid: f60b917c-6408-48be-b911-f93b05796904
author: jaszymas
ms.author: jaszymas
ms.openlocfilehash: b79212040df67c22ae7e34cd380a1a1f1bd10773
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750619"
---
# <a name="back-up-the-service-master-key"></a><span data-ttu-id="4bba4-102">Создание резервной копии главного ключа службы</span><span class="sxs-lookup"><span data-stu-id="4bba4-102">Back Up the Service Master Key</span></span>
  <span data-ttu-id="4bba4-103">В этом разделе описано, как выполнить резервное копирование главного ключа службы [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] с помощью [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4bba4-103">This topic describes how to back-up the Service Master key in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="4bba4-104">Главный ключ службы является корневым элементом иерархии шифрования.</span><span class="sxs-lookup"><span data-stu-id="4bba4-104">The service master key is the root of the encryption hierarchy.</span></span> <span data-ttu-id="4bba4-105">Поэтому необходимо создать его резервную копию, которая должна храниться в надежном месте.</span><span class="sxs-lookup"><span data-stu-id="4bba4-105">It should be backed up and stored in a secure, off-site location.</span></span> <span data-ttu-id="4bba4-106">Создание такой резервной копии должно быть одной из первых задач администрирования, выполненных на сервере.</span><span class="sxs-lookup"><span data-stu-id="4bba4-106">Creating this backup should be one of the first administrative actions performed on the server.</span></span>  
  
 <span data-ttu-id="4bba4-107">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="4bba4-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="4bba4-108">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="4bba4-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="4bba4-109">Ограничения</span><span class="sxs-lookup"><span data-stu-id="4bba4-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="4bba4-110">Безопасность</span><span class="sxs-lookup"><span data-stu-id="4bba4-110">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="4bba4-111">Создание резервной копии главного ключа службы</span><span class="sxs-lookup"><span data-stu-id="4bba4-111">To back-up the Service Master key</span></span>](#Procedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4bba4-112">Перед началом</span><span class="sxs-lookup"><span data-stu-id="4bba4-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="4bba4-113">Ограничения</span><span class="sxs-lookup"><span data-stu-id="4bba4-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="4bba4-114">Главный ключ должен быть открыт и, таким образом, расшифрован, прежде чем производится его резервное копирование.</span><span class="sxs-lookup"><span data-stu-id="4bba4-114">The master key must be open and, therefore, decrypted before it is backed up.</span></span> <span data-ttu-id="4bba4-115">Если он зашифрован с помощью главного ключа службы, то главный ключ не нужно открывать явным образом, но если главный ключ зашифрован только с помощью пароля, он должен быть явным образом открыт.</span><span class="sxs-lookup"><span data-stu-id="4bba4-115">If it is encrypted with the service master key, the master key does not have to be explicitly opened; however, if the master key is encrypted only with a password, it must be explicitly opened.</span></span>  
  
-   <span data-ttu-id="4bba4-116">Рекомендуется создать резервную копию главного ключа сразу же после его создания и затем сохранить в надежном месте.</span><span class="sxs-lookup"><span data-stu-id="4bba4-116">We recommend that you back up the master key as soon as it is created, and store the backup in a secure, off-site location.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="4bba4-117">безопасность</span><span class="sxs-lookup"><span data-stu-id="4bba4-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="4bba4-118">Permissions</span><span class="sxs-lookup"><span data-stu-id="4bba4-118">Permissions</span></span>  
 <span data-ttu-id="4bba4-119">Требует разрешения CONTROL для базы данных.</span><span class="sxs-lookup"><span data-stu-id="4bba4-119">Requires CONTROL permission on the database.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="Procedure"></a> <span data-ttu-id="4bba4-120">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4bba4-120">Using Transact-SQL</span></span>  
  
#### <a name="to-back-up-the-service-master-key"></a><span data-ttu-id="4bba4-121">Создание резервной копии главного ключа службы</span><span class="sxs-lookup"><span data-stu-id="4bba4-121">To back-up the Service Master key</span></span>  
  
1.  <span data-ttu-id="4bba4-122">В среде [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]установите соединение с экземпляром [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , содержащим главный ключ службы, для которого необходимо создать резервную копию.</span><span class="sxs-lookup"><span data-stu-id="4bba4-122">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], connect to the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance containing the service master key you wish to back up.</span></span>  
  
2.  <span data-ttu-id="4bba4-123">Задайте пароль, который будет использоваться для шифрования главного ключа службы на носителе данных резервных копий.</span><span class="sxs-lookup"><span data-stu-id="4bba4-123">Choose a password that will be used to encrypt the service master key on the backup medium.</span></span> <span data-ttu-id="4bba4-124">Пароль проходит проверку сложности.</span><span class="sxs-lookup"><span data-stu-id="4bba4-124">This password is subject to complexity checks.</span></span> <span data-ttu-id="4bba4-125">Дополнительные сведения см. в разделе [Политика паролей](../password-policy.md).</span><span class="sxs-lookup"><span data-stu-id="4bba4-125">For more information, see [Password Policy](../password-policy.md).</span></span>  
  
3.  <span data-ttu-id="4bba4-126">Получите съемный носитель данных резервной копии для хранения главного ключа.</span><span class="sxs-lookup"><span data-stu-id="4bba4-126">Obtain a removable backup medium for storing a copy of the backed-up key.</span></span>  
  
4.  <span data-ttu-id="4bba4-127">Укажите каталог NTFS, в котором будет создана резервная копия главного ключа.</span><span class="sxs-lookup"><span data-stu-id="4bba4-127">Identify an NTFS directory in which to create the backup of the key.</span></span> <span data-ttu-id="4bba4-128">В этом каталоге будет сохранен файл, созданный в следующем шаге.</span><span class="sxs-lookup"><span data-stu-id="4bba4-128">This is where you will create the file specified in the next step.</span></span> <span data-ttu-id="4bba4-129">Он должен быть защищен с помощью списка управления доступом со строгими ограничениями.</span><span class="sxs-lookup"><span data-stu-id="4bba4-129">The directory should be protected with highly restrictive access control lists (ACLs).</span></span>  
  
5.  <span data-ttu-id="4bba4-130">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4bba4-130">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
6.  <span data-ttu-id="4bba4-131">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="4bba4-131">On the Standard bar, click **New Query**.</span></span>  
  
7.  <span data-ttu-id="4bba4-132">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="4bba4-132">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Creates a backup of the "AdventureWorks2012" master key.  
    -- Because this master key is not encrypted by the service master key, a password must be specified when it is opened.  
    USE AdventureWorks2012;  
    GO  
    BACKUP SERVICE MASTER KEY TO FILE = 'c:\temp_backups\keys\service_master_ key'   
        ENCRYPTION BY PASSWORD = '3dH85Hhk003GHk2597gheij4';  
    GO  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="4bba4-133">Путь к файлу ключа и пароль ключа (если он существует) будет отличаться от вышеуказанного.</span><span class="sxs-lookup"><span data-stu-id="4bba4-133">The file path to the key and the key's password (if it exists) will be different than what is indicated above.</span></span> <span data-ttu-id="4bba4-134">Убедитесь, что оба этих параметра соответствуют вашему серверу и ключу.</span><span class="sxs-lookup"><span data-stu-id="4bba4-134">Make sure that both are specific to your server and key set-up.</span></span>  
  
8.  <span data-ttu-id="4bba4-135">Скопируйте файл на носитель данных резервных копий и проверьте правильность копирования.</span><span class="sxs-lookup"><span data-stu-id="4bba4-135">Copy the file to the backup medium and verify the copy.</span></span>  
  
9. <span data-ttu-id="4bba4-136">Сохраните резервную копию в надежном месте вне системы.</span><span class="sxs-lookup"><span data-stu-id="4bba4-136">Store the backup in a secure, off-site location.</span></span>  
  
 <span data-ttu-id="4bba4-137">Дополнительные сведения см. в разделах [OPEN MASTER KEY (Transact-SQL)](/sql/t-sql/statements/open-master-key-transact-sql) и [BACKUP MASTER KEY (Transact-SQL)](/sql/t-sql/statements/backup-master-key-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4bba4-137">For more information, see [OPEN MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/open-master-key-transact-sql) and [BACKUP MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-master-key-transact-sql).</span></span>  
  
  
