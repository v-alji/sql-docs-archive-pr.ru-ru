---
title: Репликация данных в зашифрованных столбцах (среда SQL Server Management Studio) | Документация Майкрософт
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- encryption [SQL Server], replicating data
- encryption [SQL Server replication]
- publishing [SQL Server replication], encrypted columns
ms.assetid: d1f8f586-e5a3-4a71-9391-11198d42bfa3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2e1528d81faa352fdcdf37abe9ad93fda190445c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732566"
---
# <a name="replicate-data-in-encrypted-columns-sql-server-management-studio"></a><span data-ttu-id="eaca7-102">Репликация данных в зашифрованные столбцы (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="eaca7-102">Replicate Data in Encrypted Columns (SQL Server Management Studio)</span></span>
  <span data-ttu-id="eaca7-103">Репликация позволяет публиковать данные зашифрованных столбцов.</span><span class="sxs-lookup"><span data-stu-id="eaca7-103">Replication enables you to publish encrypted column data.</span></span> <span data-ttu-id="eaca7-104">Для расшифровки и использования этих данных на подписчике ключ, который был использован при шифровании данных на издателе, должен также располагаться и на подписчике.</span><span class="sxs-lookup"><span data-stu-id="eaca7-104">To decrypt and use this data at the Subscriber, the key that was used to encrypt the data at the Publisher must also be present on the Subscriber.</span></span> <span data-ttu-id="eaca7-105">Репликация не предоставляет безопасного механизма для передачи ключей шифрования.</span><span class="sxs-lookup"><span data-stu-id="eaca7-105">Replication does not provide a secure mechanism to transport encryption keys.</span></span> <span data-ttu-id="eaca7-106">Необходимо вручную повторно создать ключ шифрования на подписчике.</span><span class="sxs-lookup"><span data-stu-id="eaca7-106">You must manually re-create the encryption key at the Subscriber.</span></span> <span data-ttu-id="eaca7-107">В данном разделе показано, как зашифровать столбец на издателе и убедиться в том, что ключ шифрования доступен на подписчике.</span><span class="sxs-lookup"><span data-stu-id="eaca7-107">This topic shows you how to encrypt a column at the Publisher and make sure that the encryption key is available at the Subscriber.</span></span>  
  
 <span data-ttu-id="eaca7-108">Основными шагами являются следующие:</span><span class="sxs-lookup"><span data-stu-id="eaca7-108">The basic steps are as follows:</span></span>  
  
1.  <span data-ttu-id="eaca7-109">Создание симметричного ключа на издателе.</span><span class="sxs-lookup"><span data-stu-id="eaca7-109">Create the symmetric key at the Publisher.</span></span>  
  
2.  <span data-ttu-id="eaca7-110">Шифрование данных столбца с помощью симметричного ключа.</span><span class="sxs-lookup"><span data-stu-id="eaca7-110">Encrypt column data with the symmetric key.</span></span>  
  
3.  <span data-ttu-id="eaca7-111">Публикация таблицы с зашифрованным столбцом.</span><span class="sxs-lookup"><span data-stu-id="eaca7-111">Publish the table with the encrypted column.</span></span>  
  
4.  <span data-ttu-id="eaca7-112">Подписка на эту публикацию.</span><span class="sxs-lookup"><span data-stu-id="eaca7-112">Subscribe to the publication.</span></span>  
  
5.  <span data-ttu-id="eaca7-113">Инициализация подписки.</span><span class="sxs-lookup"><span data-stu-id="eaca7-113">Initialize the subscription.</span></span>  
  
6.  <span data-ttu-id="eaca7-114">Повторное создание симметричного ключа на подписчике с использованием тех же самых значений для ALGORITHM, KEY_SOURCE и IDENTITY_VALUE, что и в первом шаге.</span><span class="sxs-lookup"><span data-stu-id="eaca7-114">Recreate the symmetric key at the Subscriber using same values for ALGORITHM, KEY_SOURCE, and IDENTITY_VALUE as in step 1.</span></span>  
  
7.  <span data-ttu-id="eaca7-115">Получение доступа к данным зашифрованного столбца.</span><span class="sxs-lookup"><span data-stu-id="eaca7-115">Access the encrypted column data.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="eaca7-116">Для шифрования данных столбца следует использовать симметричный ключ.</span><span class="sxs-lookup"><span data-stu-id="eaca7-116">You should use a symmetric key to encrypt column data.</span></span> <span data-ttu-id="eaca7-117">Симметричный ключ сам по себе может быть защищен на издателе и подписчике различными способами.</span><span class="sxs-lookup"><span data-stu-id="eaca7-117">The symmetric key itself can be secured by different means at the Publisher and Subscriber.</span></span>  
  
### <a name="to-create-and-replicate-encrypted-column-data"></a><span data-ttu-id="eaca7-118">Создание и репликация данных зашифрованного столбца</span><span class="sxs-lookup"><span data-stu-id="eaca7-118">To create and replicate encrypted column data</span></span>  
  
1.  <span data-ttu-id="eaca7-119">На издателе выполните инструкцию [CREATE SYMMETRIC KEY](/sql/t-sql/statements/create-symmetric-key-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="eaca7-119">At the Publisher, execute [CREATE SYMMETRIC KEY](/sql/t-sql/statements/create-symmetric-key-transact-sql).</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="eaca7-120">Значение KEY_SOURCE является важным значением, которое может быть использовано для повторного создания симметричного ключа и расшифровки данных.</span><span class="sxs-lookup"><span data-stu-id="eaca7-120">The value of KEY_SOURCE is valuable data that can be used to re-create the symmetric key and decrypt data.</span></span> <span data-ttu-id="eaca7-121">Значение KEY_SOURCE должно всегда храниться и передаваться с соблюдением всех мер предосторожности.</span><span class="sxs-lookup"><span data-stu-id="eaca7-121">KEY_SOURCE must always be stored and transported securely.</span></span>  
  
2.  <span data-ttu-id="eaca7-122">Чтобы открыть новый ключ, выполните инструкцию [OPEN SYMMETRIC KEY](/sql/t-sql/statements/open-symmetric-key-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="eaca7-122">Execute [OPEN SYMMETRIC KEY](/sql/t-sql/statements/open-symmetric-key-transact-sql) to open the new key.</span></span>  
  
3.  <span data-ttu-id="eaca7-123">Для шифрования данных столбца на издателе используйте функцию [EncryptByKey](/sql/t-sql/functions/encryptbykey-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="eaca7-123">Use the [EncryptByKey](/sql/t-sql/functions/encryptbykey-transact-sql) function to encrypt column data at the Publisher.</span></span>  
  
4.  <span data-ttu-id="eaca7-124">Чтобы закрыть ключ, выполните инструкцию [CLOSE SYMMETRIC KEY](/sql/t-sql/statements/close-symmetric-key-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="eaca7-124">Execute [CLOSE SYMMETRIC KEY](/sql/t-sql/statements/close-symmetric-key-transact-sql) to close the key.</span></span>  
  
5.  <span data-ttu-id="eaca7-125">Опубликуйте таблицу, которая содержит зашифрованный столбец.</span><span class="sxs-lookup"><span data-stu-id="eaca7-125">Publish the table that contains the encrypted column.</span></span> <span data-ttu-id="eaca7-126">Дополнительные сведения см. в разделе [Create a Publication](../publish/create-a-publication.md).</span><span class="sxs-lookup"><span data-stu-id="eaca7-126">For more information, see [Create a Publication](../publish/create-a-publication.md).</span></span>  
  
6.  <span data-ttu-id="eaca7-127">Подписка на эту публикацию.</span><span class="sxs-lookup"><span data-stu-id="eaca7-127">Subscribe to the publication.</span></span> <span data-ttu-id="eaca7-128">Дополнительные сведения см. в статьях [Создание подписки по запросу](../create-a-pull-subscription.md) и [Создание принудительной подписки](../create-a-push-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="eaca7-128">For more information, see [Create a Pull Subscription](../create-a-pull-subscription.md) or [Create a Push Subscription](../create-a-push-subscription.md).</span></span>  
  
7.  <span data-ttu-id="eaca7-129">Инициализация подписки.</span><span class="sxs-lookup"><span data-stu-id="eaca7-129">Initialize the subscription.</span></span> <span data-ttu-id="eaca7-130">Дополнительные сведения см. в разделе [Create and Apply the Initial Snapshot](../create-and-apply-the-initial-snapshot.md).</span><span class="sxs-lookup"><span data-stu-id="eaca7-130">For more information, see [Create and Apply the Initial Snapshot](../create-and-apply-the-initial-snapshot.md).</span></span>  
  
8.  <span data-ttu-id="eaca7-131">На подписчике выполните инструкцию [CREATE SYMMETRIC KEY](/sql/t-sql/statements/create-symmetric-key-transact-sql) , используя те же самые значения для ALGORITHM, KEY_SOURCE и IDENTITY_VALUE, что и в первом шаге.</span><span class="sxs-lookup"><span data-stu-id="eaca7-131">At the Subscriber, execute [CREATE SYMMETRIC KEY](/sql/t-sql/statements/create-symmetric-key-transact-sql) using the same values for ALGORITHM, KEY_SOURCE, and IDENTITY_VALUE as in step 1.</span></span> <span data-ttu-id="eaca7-132">При этом можно задать иное значение в предложении ENCRYPTION BY.</span><span class="sxs-lookup"><span data-stu-id="eaca7-132">You can specify a different value for ENCRYPTION BY.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="eaca7-133">Значение KEY_SOURCE является важным значением, которое может быть использовано для повторного создания симметричного ключа и расшифровки данных.</span><span class="sxs-lookup"><span data-stu-id="eaca7-133">The value of KEY_SOURCE is valuable data that can be used to re-create the symmetric key and decrypt data.</span></span> <span data-ttu-id="eaca7-134">Значение KEY_SOURCE должно всегда храниться и передаваться с соблюдением всех мер предосторожности.</span><span class="sxs-lookup"><span data-stu-id="eaca7-134">KEY_SOURCE must always be stored and transported securely.</span></span>  
  
9. <span data-ttu-id="eaca7-135">Чтобы открыть новый ключ, выполните инструкцию [OPEN SYMMETRIC KEY](/sql/t-sql/statements/open-symmetric-key-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="eaca7-135">Execute [OPEN SYMMETRIC KEY](/sql/t-sql/statements/open-symmetric-key-transact-sql) to open the new key.</span></span>  
  
10. <span data-ttu-id="eaca7-136">Для расшифровки реплицируемых данных на подписчике используйте функцию [DecryptByKey](/sql/t-sql/functions/decryptbykey-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="eaca7-136">Use the [DecryptByKey](/sql/t-sql/functions/decryptbykey-transact-sql) function to decrypt replicated data at the Subscriber.</span></span>  
  
11. <span data-ttu-id="eaca7-137">Чтобы закрыть ключ, выполните инструкцию [CLOSE SYMMETRIC KEY](/sql/t-sql/statements/close-symmetric-key-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="eaca7-137">Execute [CLOSE SYMMETRIC KEY](/sql/t-sql/statements/close-symmetric-key-transact-sql) to close the key.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eaca7-138">Пример</span><span class="sxs-lookup"><span data-stu-id="eaca7-138">Example</span></span>  
 <span data-ttu-id="eaca7-139">В этом примере создается симметричный ключ, сертификат, который используется для обеспечения безопасности симметричного ключа, и главный ключ.</span><span class="sxs-lookup"><span data-stu-id="eaca7-139">This example creates a symmetric key, a certificate that is used to help secure the symmetric key, and a master key.</span></span> <span data-ttu-id="eaca7-140">Эти ключи создаются в базе данных публикации.</span><span class="sxs-lookup"><span data-stu-id="eaca7-140">These keys are created in the publication database.</span></span> <span data-ttu-id="eaca7-141">В последующем они используются для создания зашифрованного столбца EncryptedCreditCardApprovalCode в таблице `SalesOrderHeader` .</span><span class="sxs-lookup"><span data-stu-id="eaca7-141">They are then used to create an encrypted column (EncryptedCreditCardApprovalCode) in the `SalesOrderHeader` table.</span></span> <span data-ttu-id="eaca7-142">Этот столбец опубликован в публикации AdvWorksSalesOrdersMerge вместо незашифрованного столбца CreditCardApprovalCode.</span><span class="sxs-lookup"><span data-stu-id="eaca7-142">This column is published in the AdvWorksSalesOrdersMerge publication instead of the unencrypted CreditCardApprovalCode column.</span></span> <span data-ttu-id="eaca7-143">По возможности предлагайте пользователям вводить учетные данные системы безопасности во время выполнения приложения.</span><span class="sxs-lookup"><span data-stu-id="eaca7-143">When possible, prompt users to enter security credentials at runtime.</span></span> <span data-ttu-id="eaca7-144">В случае необходимости хранения учетных данных в файле скрипта этот файл следует защищать во избежание несанкционированного доступа.</span><span class="sxs-lookup"><span data-stu-id="eaca7-144">If you must store credentials in a script file, you must secure the file to prevent unauthorized access.</span></span>  
  
 [!code-sql[HowTo#sp_PublishEncryptedColumn](../../../snippets/tsql/SQL15/replication/howto/tsql/publishencryptedcolumn.sql#sp_publishencryptedcolumn)]  
  
 [!code-sql[HowTo#sp_AddMergeArticle](../../../snippets/tsql/SQL15/replication/howto/tsql/createmergepub.sql#sp_addmergearticle)]  
  
## <a name="example"></a><span data-ttu-id="eaca7-145">Пример</span><span class="sxs-lookup"><span data-stu-id="eaca7-145">Example</span></span>  
 <span data-ttu-id="eaca7-146">В этом примере повторно создается тот же самый симметричный ключ в базе данных подписки с помощью тех же самых значений для ALGORITHM, KEY_SOURCE и IDENTITY_VALUE, что и в первом шаге.</span><span class="sxs-lookup"><span data-stu-id="eaca7-146">This example recreates the same symmetric key in the subscription database using the same values for ALGORITHM, KEY_SOURCE, and IDENTITY_VALUE from the first example.</span></span> <span data-ttu-id="eaca7-147">В этом примере предполагается, что уже имеется инициализированная подписка на публикацию AdvWorksSalesOrdersMerge для репликации зашифрованного столбца.</span><span class="sxs-lookup"><span data-stu-id="eaca7-147">This example assumes that you have already initialized a subscription to the AdvWorksSalesOrdersMerge publication to replicate the encrypted column.</span></span> <span data-ttu-id="eaca7-148">По возможности предлагайте пользователям вводить учетные данные системы безопасности во время выполнения приложения.</span><span class="sxs-lookup"><span data-stu-id="eaca7-148">When possible, prompt users to enter security credentials at runtime.</span></span> <span data-ttu-id="eaca7-149">Если необходимо хранить учетные данные в файле скрипта, следует защитить этот файл во время хранения и передачи, чтобы предотвратить несанкционированный доступ к нему.</span><span class="sxs-lookup"><span data-stu-id="eaca7-149">If you must store credentials in a script file, you must secure the file during storage and transport to prevent unauthorized access.</span></span>  
  
 [!code-sql[HowTo#sp_SubscriberEncryptedColumn](../../../snippets/tsql/SQL15/replication/howto/tsql/subscriberencryptedcolumn.sql#sp_subscriberencryptedcolumn)]  
  
## <a name="see-also"></a><span data-ttu-id="eaca7-150">См. также:</span><span class="sxs-lookup"><span data-stu-id="eaca7-150">See Also</span></span>  
 <span data-ttu-id="eaca7-151">[Безопасность Репликация SQL Server](view-and-modify-replication-security-settings.md) </span><span class="sxs-lookup"><span data-stu-id="eaca7-151">[SQL Server Replication Security](view-and-modify-replication-security-settings.md) </span></span>  
 [<span data-ttu-id="eaca7-152">Создание идентичных симметричных ключей на двух серверах</span><span class="sxs-lookup"><span data-stu-id="eaca7-152">Create Identical Symmetric Keys on Two Servers</span></span>](../../security/encryption/create-identical-symmetric-keys-on-two-servers.md)  
  
  
