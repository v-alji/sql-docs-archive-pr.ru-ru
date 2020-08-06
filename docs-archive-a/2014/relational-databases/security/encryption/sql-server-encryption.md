---
title: Шифрование в SQL Server | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- encryption [SQL Server], about encryption
- security [SQL Server], encryption
- cryptography [SQL Server], about cryptography
ms.assetid: ead0150e-4943-4ad5-84c8-36f85c7278f4
author: jaszymas
ms.author: jaszymas
ms.openlocfilehash: 6fc68e6f3280a8e23d6a1bf4f364aadfffd69f85
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752048"
---
# <a name="sql-server-encryption"></a><span data-ttu-id="f88fc-102">Шифрование SQL Server</span><span class="sxs-lookup"><span data-stu-id="f88fc-102">SQL Server Encryption</span></span>
  <span data-ttu-id="f88fc-103">Шифрование представляет собой способ скрытия данных с помощью ключа или пароля.</span><span class="sxs-lookup"><span data-stu-id="f88fc-103">Encryption is the process of obfuscating data by the use of a key or password.</span></span> <span data-ttu-id="f88fc-104">Это делает данные бесполезными без соответствующего ключа или пароля для дешифрования.</span><span class="sxs-lookup"><span data-stu-id="f88fc-104">This can make the data useless without the corresponding decryption key or password.</span></span> <span data-ttu-id="f88fc-105">Шифрование не решает проблемы управления доступом.</span><span class="sxs-lookup"><span data-stu-id="f88fc-105">Encryption does not solve access control problems.</span></span> <span data-ttu-id="f88fc-106">Однако оно повышает защиту за счет ограничения потери данных даже при обходе системы управления доступом.</span><span class="sxs-lookup"><span data-stu-id="f88fc-106">However, it enhances security by limiting data loss even if access controls are bypassed.</span></span> <span data-ttu-id="f88fc-107">Например, если компьютер, на котором установлена база данных, был настроен неправильно и злоумышленник смог получить конфиденциальные данные, то украденная информация будет бесполезна, если она была предварительно зашифрована.</span><span class="sxs-lookup"><span data-stu-id="f88fc-107">For example, if the database host computer is misconfigured and a hacker obtains sensitive data, that stolen information might be useless if it is encrypted.</span></span>  
  
 <span data-ttu-id="f88fc-108">В [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] можно шифровать соединения, данные и хранимые процедуры.</span><span class="sxs-lookup"><span data-stu-id="f88fc-108">You can use encryption in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] for connections, data, and stored procedures.</span></span> <span data-ttu-id="f88fc-109">В следующей таблице содержатся дополнительные сведения о шифровании в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f88fc-109">The following table contains more information about encryption in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f88fc-110">Несмотря на то, что шифрование является полезным средством обеспечения безопасности, его не следует применять ко всем данным или соединениям.</span><span class="sxs-lookup"><span data-stu-id="f88fc-110">Although encryption is a valuable tool to help ensure security, it should not be considered for all data or connections.</span></span> <span data-ttu-id="f88fc-111">При решении о внедрении шифрования необходимо проанализировать, как пользователи получают доступ к данным.</span><span class="sxs-lookup"><span data-stu-id="f88fc-111">When you are deciding whether to implement encryption, consider how users will access data.</span></span> <span data-ttu-id="f88fc-112">Если пользователи получают доступ к данным через открытую сеть, то шифрование может потребоваться для повышения безопасности.</span><span class="sxs-lookup"><span data-stu-id="f88fc-112">If users access data over a public network, data encryption might be required to increase security.</span></span> <span data-ttu-id="f88fc-113">Однако если весь доступ осуществляется по безопасной внутренней сети, то шифрование не требуется.</span><span class="sxs-lookup"><span data-stu-id="f88fc-113">However, if all access involves a secure intranet configuration, encryption might not be required.</span></span> <span data-ttu-id="f88fc-114">Использование шифрования включает политику управления паролями, ключами и сертификатами.</span><span class="sxs-lookup"><span data-stu-id="f88fc-114">Any use of encryption should also include a maintenance strategy for passwords, keys, and certificates.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f88fc-115">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="f88fc-115">In This Section</span></span>  
 [<span data-ttu-id="f88fc-116">Иерархия средств шифрования</span><span class="sxs-lookup"><span data-stu-id="f88fc-116">Encryption Hierarchy</span></span>](encryption-hierarchy.md)  
 <span data-ttu-id="f88fc-117">Сведения об иерархии шифрования в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f88fc-117">Information about the encryption hierarchy in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="f88fc-118">Выбор алгоритма шифрования</span><span class="sxs-lookup"><span data-stu-id="f88fc-118">Choose an Encryption Algorithm</span></span>](choose-an-encryption-algorithm.md)  
 <span data-ttu-id="f88fc-119">Сведения о выборе эффективного алгоритма шифрования.</span><span class="sxs-lookup"><span data-stu-id="f88fc-119">Information about how to select an effective encrypting algorithm.</span></span>  
  
 [<span data-ttu-id="f88fc-120">Прозрачное шифрование данных (TDE)</span><span class="sxs-lookup"><span data-stu-id="f88fc-120">Transparent Data Encryption &#40;TDE&#41;</span></span>](transparent-data-encryption.md)  
 <span data-ttu-id="f88fc-121">Общие сведения о прозрачном шифровании данных.</span><span class="sxs-lookup"><span data-stu-id="f88fc-121">General information about how to encrypt data transparently.</span></span>  
  
 [<span data-ttu-id="f88fc-122">Ключи шифрования базы данных и SQL Server &#40;ядро СУБД&#41;</span><span class="sxs-lookup"><span data-stu-id="f88fc-122">SQL Server and Database Encryption Keys &#40;Database Engine&#41;</span></span>](sql-server-and-database-encryption-keys-database-engine.md)  
 <span data-ttu-id="f88fc-123">Используемые в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]ключи шифрования представляют собой сочетание открытых, закрытых и симметричных ключей, которые используются для защиты конфиденциальных данных.</span><span class="sxs-lookup"><span data-stu-id="f88fc-123">In [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], encryption keys include a combination of public, private, and symmetric keys that are used to protect sensitive data.</span></span> <span data-ttu-id="f88fc-124">В этом разделе рассказывается о внедрении и управлении ключами шифрования.</span><span class="sxs-lookup"><span data-stu-id="f88fc-124">This section explains how to implement and manage encryption keys.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="f88fc-125">См. также</span><span class="sxs-lookup"><span data-stu-id="f88fc-125">Related Content</span></span>  
 [<span data-ttu-id="f88fc-126">Обеспечение безопасности SQL Server</span><span class="sxs-lookup"><span data-stu-id="f88fc-126">Securing SQL Server</span></span>](../securing-sql-server.md)  
 <span data-ttu-id="f88fc-127">Общие сведения о способах обеспечения безопасности платформы [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] и способах работы с пользователями и защищаемыми объектами.</span><span class="sxs-lookup"><span data-stu-id="f88fc-127">Overview of how to help secure the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] platform, and how to work with users and securable objects.</span></span>  
  
 [<span data-ttu-id="f88fc-128">Криптографические функции (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="f88fc-128">Cryptographic Functions &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/cryptographic-functions-transact-sql)  
 <span data-ttu-id="f88fc-129">Сведения о внедрении криптографических функций.</span><span class="sxs-lookup"><span data-stu-id="f88fc-129">Information about how to implement cryptographic functions.</span></span>  
  
 [<span data-ttu-id="f88fc-130">ENCRYPTBYPASSPHRASE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="f88fc-130">ENCRYPTBYPASSPHRASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/encryptbypassphrase-transact-sql)  
 <span data-ttu-id="f88fc-131">Сведения об использовании паролей для шифрования данных.</span><span class="sxs-lookup"><span data-stu-id="f88fc-131">Information about how to use a password to encrypt data.</span></span>  
  
 [<span data-ttu-id="f88fc-132">ENCRYPTBYKEY (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="f88fc-132">ENCRYPTBYKEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/encryptbykey-transact-sql)  
 <span data-ttu-id="f88fc-133">Сведения об использовании симметричных ключей для шифрования данных.</span><span class="sxs-lookup"><span data-stu-id="f88fc-133">Information about how to use a symmetric key to encrypt data.</span></span>  
  
 [<span data-ttu-id="f88fc-134">ENCRYPTBYASYMKEY (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="f88fc-134">ENCRYPTBYASYMKEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/encryptbyasymkey-transact-sql)  
 <span data-ttu-id="f88fc-135">Сведения об использовании асимметричных ключей для шифрования данных.</span><span class="sxs-lookup"><span data-stu-id="f88fc-135">Information about how to use an asymmetric key to encrypt data.</span></span>  
  
 [<span data-ttu-id="f88fc-136">ENCRYPTBYCERT (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="f88fc-136">ENCRYPTBYCERT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/encryptbycert-transact-sql)  
 <span data-ttu-id="f88fc-137">Сведения об использовании сертификатов для шифрования данных.</span><span class="sxs-lookup"><span data-stu-id="f88fc-137">Information about how to use a certificate to encrypt data.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="f88fc-138">Внешние ресурсы</span><span class="sxs-lookup"><span data-stu-id="f88fc-138">External Resources</span></span>  
 [<span data-ttu-id="f88fc-139">10 действий по SQL Server безопасности 2005</span><span class="sxs-lookup"><span data-stu-id="f88fc-139">10 Steps to SQL Server 2005 Security</span></span>](https://www.itprotoday.com/sql-server/10-steps-sql-server-2005-security)  
 <span data-ttu-id="f88fc-140">Текущие сведения о безопасности в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f88fc-140">Current information about [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] security.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f88fc-141">См. также:</span><span class="sxs-lookup"><span data-stu-id="f88fc-141">See Also</span></span>  
 <span data-ttu-id="f88fc-142">[sys.key_encryptions (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-key-encryptions-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f88fc-142">[sys.key_encryptions &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-key-encryptions-transact-sql) </span></span>  
 <span data-ttu-id="f88fc-143">[Ключи шифрования базы данных и SQL Server (ядро СУБД)](sql-server-and-database-encryption-keys-database-engine.md) </span><span class="sxs-lookup"><span data-stu-id="f88fc-143">[SQL Server and Database Encryption Keys &#40;Database Engine&#41;](sql-server-and-database-encryption-keys-database-engine.md) </span></span>  
 [<span data-ttu-id="f88fc-144">Резервное копирование и восстановление ключей шифрования служб Reporting Services</span><span class="sxs-lookup"><span data-stu-id="f88fc-144">Back Up and Restore Reporting Services Encryption Keys</span></span>](../../../reporting-services/install-windows/ssrs-encryption-keys-back-up-and-restore-encryption-keys.md)  
  
  
