---
title: Выбор алгоритма шифрования | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- cryptography [SQL Server], algorithms
- encryption [SQL Server], algorithms
- security [SQL Server], encryption
- algorithms [SQL Server encryption]
ms.assetid: 8227028c-a9c9-489d-bd27-fbf8242634ae
author: jaszymas
ms.author: jaszymas
ms.openlocfilehash: 3b2c5292b4a00a3ad81e53fdbc603bb584130613
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750620"
---
# <a name="choose-an-encryption-algorithm"></a><span data-ttu-id="edc98-102">Выбор алгоритма шифрования</span><span class="sxs-lookup"><span data-stu-id="edc98-102">Choose an Encryption Algorithm</span></span>
  <span data-ttu-id="edc98-103">Шифрование — одно из нескольких эффективных средств защиты, позволяющих администраторам обеспечивать безопасность экземпляра [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="edc98-103">Encryption is one of several defenses-in-depth that are available to the administrator who wants to secure an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="edc98-104">Алгоритмы шифрования определяют преобразования данных, которые не могут с легкостью отменить неавторизованные пользователи.</span><span class="sxs-lookup"><span data-stu-id="edc98-104">Encryption algorithms define data transformations that cannot be easily reversed by unauthorized users.</span></span> [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="edc98-105">позволяет администраторам и разработчикам выбирать из нескольких алгоритмов, в том числе DES, Triple DES, TRIPLE_DES_3KEY, RC2, RC4, RC4 со 128-разрядным ключом, DESX, AES со 128-разрядным ключом, AES со 192-разрядным ключом и AES с 256-разрядным ключом.</span><span class="sxs-lookup"><span data-stu-id="edc98-105">allows administrators and developers to choose from among several algorithms, including DES, Triple DES, TRIPLE_DES_3KEY, RC2, RC4, 128-bit RC4, DESX, 128-bit AES, 192-bit AES, and 256-bit AES.</span></span>  
  
 <span data-ttu-id="edc98-106">Не существует одного алгоритма, идеально подходящего для всех случаев. Информация по качеству каждого из них лежит за пределами электронной документации по [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="edc98-106">No single algorithm is ideal for all situations, and guidance on the merits of each is beyond the scope of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Books Online.</span></span> <span data-ttu-id="edc98-107">Однако можно руководствоваться следующими общими принципами:</span><span class="sxs-lookup"><span data-stu-id="edc98-107">However, the following general principles apply:</span></span>  
  
-   <span data-ttu-id="edc98-108">Надежные алгоритмы шифрования обычно потребляют больше ресурсов ЦП, чем менее надежные средства шифрования.</span><span class="sxs-lookup"><span data-stu-id="edc98-108">Strong encryption generally consumes more CPU resources than weak encryption.</span></span>  
  
-   <span data-ttu-id="edc98-109">Использование длинных ключей, как правило, дает более надежные результаты, чем шифрование с помощью коротких ключей.</span><span class="sxs-lookup"><span data-stu-id="edc98-109">Long keys generally yield stronger encryption than short keys.</span></span>  
  
-   <span data-ttu-id="edc98-110">Асимметричное шифрование слабее симметричного шифрования с использованием ключа той же длины, но является относительно медленным.</span><span class="sxs-lookup"><span data-stu-id="edc98-110">Asymmetric encryption is weaker than symmetric encryption using the same key length, but it is relatively slow.</span></span>  
  
-   <span data-ttu-id="edc98-111">Блочные шифры с длинными ключами надежнее поточных шифров.</span><span class="sxs-lookup"><span data-stu-id="edc98-111">Block ciphers with long keys are stronger than stream ciphers.</span></span>  
  
-   <span data-ttu-id="edc98-112">Длинные сложные пароли надежнее, чем короткие пароли.</span><span class="sxs-lookup"><span data-stu-id="edc98-112">Long, complex passwords are stronger than short passwords.</span></span>  
  
-   <span data-ttu-id="edc98-113">При необходимости шифровать большие объемы данных, шифруйте данные с помощью симметричного ключа, а симметричный ключ — с помощью асимметричного ключа.</span><span class="sxs-lookup"><span data-stu-id="edc98-113">If you are encrypting lots of data, you should encrypt the data using a symmetric key, and encrypt the symmetric key with an asymmetric key.</span></span>  
  
-   <span data-ttu-id="edc98-114">Зашифрованные данные не поддаются сжатию, но сжатые данные могут быть зашифрованы.</span><span class="sxs-lookup"><span data-stu-id="edc98-114">Encrypted data cannot be compressed, but compressed data can be encrypted.</span></span> <span data-ttu-id="edc98-115">При использовании сжатия данных, выполняйте эту операцию до их шифрования.</span><span class="sxs-lookup"><span data-stu-id="edc98-115">If you use compression, you should compress data before encrypting it.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="edc98-116">Алгоритм RC4 поддерживается только в целях обратной совместимости.</span><span class="sxs-lookup"><span data-stu-id="edc98-116">The RC4 algorithm is only supported for backward compatibility.</span></span> <span data-ttu-id="edc98-117">Когда база данных имеет уровень совместимости 90 или 100, новые материалы могут шифроваться только с помощью алгоритмов RC4 или RC4_128.</span><span class="sxs-lookup"><span data-stu-id="edc98-117">New material can only be encrypted using RC4 or RC4_128 when the database is in compatibility level 90 or 100.</span></span> <span data-ttu-id="edc98-118">(Не рекомендуется.) Используйте вместо этого более новые алгоритмы, например AES.</span><span class="sxs-lookup"><span data-stu-id="edc98-118">(Not recommended.) Use a newer algorithm such as one of the AES algorithms instead.</span></span> <span data-ttu-id="edc98-119">В [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] и более поздних версиях материалы, зашифрованные с помощью алгоритмов RC4 или RC4_128, могут быть расшифрованы на любом уровне совместимости.</span><span class="sxs-lookup"><span data-stu-id="edc98-119">In [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] and higher material encrypted using RC4 or RC4_128 can be decrypted in any compatibility level.</span></span>  
>   
>  <span data-ttu-id="edc98-120">Многократное использование одного и того же RC4 или RC4_128 KEY_GUID для различных блоков данных приведет к одному и тому же ключу RC4, так как [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] не предоставляет рассеивание автоматически.</span><span class="sxs-lookup"><span data-stu-id="edc98-120">Repeated use of the same RC4 or RC4_128 KEY_GUID on different blocks of data will result in the same RC4 key because [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] does not provide a salt automatically.</span></span> <span data-ttu-id="edc98-121">Повторное использование ключа RC4 является типичной ошибкой, снижающей надежность шифра.</span><span class="sxs-lookup"><span data-stu-id="edc98-121">Using the same RC4 key repeatedly is a well-known error that will result in very weak encryption.</span></span> <span data-ttu-id="edc98-122">Таким образом, ключевые слова RC4 и RC4_128 являются устаревшими.</span><span class="sxs-lookup"><span data-stu-id="edc98-122">Therefore, we have deprecated the RC4 and RC4_128 keywords.</span></span> [!INCLUDE[ssNoteDepFutureDontUse](../../../includes/ssnotedepfuturedontuse-md.md)]  
  
 <span data-ttu-id="edc98-123">Дополнительные сведения об алгоритмах шифрования и о технологии шифрования см. в разделе [Основные понятия безопасности](https://go.microsoft.com/fwlink/?LinkId=62082) руководства разработчика для платформы .NET Framework в сети MSDN.</span><span class="sxs-lookup"><span data-stu-id="edc98-123">For more information about encryption algorithms and encryption technology, see [Key Security Concepts](https://go.microsoft.com/fwlink/?LinkId=62082) in the .NET Framework Developer's Guide on MSDN.</span></span>  
  
 <span data-ttu-id="edc98-124">**Пояснение к алгоритмам DES:**</span><span class="sxs-lookup"><span data-stu-id="edc98-124">**Clarification regarding DES algorithms:**</span></span>  
  
-   <span data-ttu-id="edc98-125">DESX был именован неправильно.</span><span class="sxs-lookup"><span data-stu-id="edc98-125">DESX was incorrectly named.</span></span> <span data-ttu-id="edc98-126">Симметричные ключи, созданные с параметром ALGORITHM = DESX, в действительности используют шифр TRIPLE DES с 192-битным ключом.</span><span class="sxs-lookup"><span data-stu-id="edc98-126">Symmetric keys created with ALGORITHM = DESX actually use the TRIPLE DES cipher with a 192-bit key.</span></span> <span data-ttu-id="edc98-127">Алгоритм DESX не предоставляется.</span><span class="sxs-lookup"><span data-stu-id="edc98-127">The DESX algorithm is not provided.</span></span> [!INCLUDE[ssNoteDepFutureAvoid](../../../includes/ssnotedepfutureavoid-md.md)]  
  
-   <span data-ttu-id="edc98-128">Симметричные ключи, созданные с параметром ALGORITHM = TRIPLE_DES_3KEY, используют шифр TRIPLE DES с 192-битным ключом.</span><span class="sxs-lookup"><span data-stu-id="edc98-128">Symmetric keys created with ALGORITHM = TRIPLE_DES_3KEY use TRIPLE DES with a 192-bit key.</span></span>  
  
-   <span data-ttu-id="edc98-129">Симметричные ключи, созданные с параметром ALGORITHM = TRIPLE_DES, используют шифр TRIPLE DES с 128-битным ключом.</span><span class="sxs-lookup"><span data-stu-id="edc98-129">Symmetric keys created with ALGORITHM = TRIPLE_DES use TRIPLE DES with a 128-bit key.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="edc98-130">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="edc98-130">Related Tasks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="edc98-131">Шифрование с помощью симметричного ключа.</span><span class="sxs-lookup"><span data-stu-id="edc98-131">Encrypting using a symmetric key.</span></span>|[<span data-ttu-id="edc98-132">CREATE SYMMETRIC KEY (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="edc98-132">CREATE SYMMETRIC KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-symmetric-key-transact-sql)|  
|<span data-ttu-id="edc98-133">Шифрование с помощью асимметричного ключа.</span><span class="sxs-lookup"><span data-stu-id="edc98-133">Encrypting using an asymmetric key.</span></span>|[<span data-ttu-id="edc98-134">CREATE ASYMMETRIC KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="edc98-134">CREATE ASYMMETRIC KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-asymmetric-key-transact-sql)|  
|<span data-ttu-id="edc98-135">Кодирование с использованием сертификата.</span><span class="sxs-lookup"><span data-stu-id="edc98-135">Encrypting using a certificate.</span></span>|[<span data-ttu-id="edc98-136">CREATE CERTIFICATE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="edc98-136">CREATE CERTIFICATE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-certificate-transact-sql)|  
|<span data-ttu-id="edc98-137">Шифрование файлов базы данных с помощью прозрачного шифрования данных.</span><span class="sxs-lookup"><span data-stu-id="edc98-137">Encrypting database files using transparent data encryption.</span></span>|[<span data-ttu-id="edc98-138">Прозрачное шифрование данных (TDE)</span><span class="sxs-lookup"><span data-stu-id="edc98-138">Transparent Data Encryption &#40;TDE&#41;</span></span>](transparent-data-encryption.md)|  
|<span data-ttu-id="edc98-139">Как зашифровать столбец таблицы.</span><span class="sxs-lookup"><span data-stu-id="edc98-139">How to encrypt one column of a table.</span></span>|[<span data-ttu-id="edc98-140">Шифрование столбца данных</span><span class="sxs-lookup"><span data-stu-id="edc98-140">Encrypt a Column of Data</span></span>](encrypt-a-column-of-data.md)|  
  
## <a name="see-also"></a><span data-ttu-id="edc98-141">См. также:</span><span class="sxs-lookup"><span data-stu-id="edc98-141">See Also</span></span>  
 <span data-ttu-id="edc98-142">[Шифрование SQL Server](sql-server-encryption.md) </span><span class="sxs-lookup"><span data-stu-id="edc98-142">[SQL Server Encryption](sql-server-encryption.md) </span></span>  
 [<span data-ttu-id="edc98-143">Иерархия средств шифрования</span><span class="sxs-lookup"><span data-stu-id="edc98-143">Encryption Hierarchy</span></span>](encryption-hierarchy.md)  
  
  
