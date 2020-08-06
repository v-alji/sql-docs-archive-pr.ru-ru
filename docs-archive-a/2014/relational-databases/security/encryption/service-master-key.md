---
title: Главный ключ службы | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- service master key [SQL Server]
- service master key [SQL Server], about service master key
ms.assetid: 85f2095d-2590-4f59-8a29-7e100edd02bb
author: jaszymas
ms.author: jaszymas
ms.openlocfilehash: baeeffd49ac89ce85cf64932fbfd4982d7243887
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752059"
---
# <a name="service-master-key"></a><span data-ttu-id="d7df0-102">главный ключ службы</span><span class="sxs-lookup"><span data-stu-id="d7df0-102">Service Master Key</span></span>
  <span data-ttu-id="d7df0-103">Главный ключ службы является корнем иерархии шифрования [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d7df0-103">The Service Master Key is the root of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] encryption hierarchy.</span></span> <span data-ttu-id="d7df0-104">Он создается автоматически, как только он впервые понадобится для шифрования другого ключа.</span><span class="sxs-lookup"><span data-stu-id="d7df0-104">It is generated automatically the first time it is needed to encrypt another key.</span></span> <span data-ttu-id="d7df0-105">По умолчанию главный ключ службы шифруется с помощью API-интерфейса защиты данных Windows и ключа локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="d7df0-105">By default, the Service Master Key is encrypted using the Windows data protection API and using the local machine key.</span></span> <span data-ttu-id="d7df0-106">Главный ключ службы может быть открыт только учетной записью службы Windows, под которой он был создан, либо участником, имеющим доступ к имени и паролю учетной записи службы.</span><span class="sxs-lookup"><span data-stu-id="d7df0-106">The Service Master Key can only be opened by the Windows service account under which it was created or by a principal with access to both the service account name and its password.</span></span>  
  
 <span data-ttu-id="d7df0-107">Для повторного создания или восстановления из копии главного ключа службы необходимо дешифровать и снова зашифровать всю иерархию шифрования.</span><span class="sxs-lookup"><span data-stu-id="d7df0-107">Regenerating or restoring the Service Master Key involves decrypting and re-encrypting the complete encryption hierarchy.</span></span> <span data-ttu-id="d7df0-108">Если только ключ не был похищен, данную ресурсоемкую операцию следует планировать на то время, когда количество обращений к серверу минимальное.</span><span class="sxs-lookup"><span data-stu-id="d7df0-108">Unless the key has been compromised, this resource-intensive operation should be scheduled during a period of low demand.</span></span>  
  
 [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] <span data-ttu-id="d7df0-109">использует для защиты главного ключа службы и главного ключа базы данных алгоритм шифрования AES.</span><span class="sxs-lookup"><span data-stu-id="d7df0-109">uses the AES encryption algorithm to protect the service master key (SMK) and the database master key (DMK).</span></span> <span data-ttu-id="d7df0-110">AES - это новый алгоритм шифрования, отличный от алгоритма 3DES, используемого в более ранних версиях.</span><span class="sxs-lookup"><span data-stu-id="d7df0-110">AES is a newer encryption algorithm than 3DES used in earlier versions.</span></span> <span data-ttu-id="d7df0-111">После обновления экземпляра компонента [!INCLUDE[ssDE](../../../includes/ssde-md.md)] до [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] необходимо заново сформировать главный ключ службы и главный ключ базы данных, чтобы обновить главные ключи до алгоритма AES.</span><span class="sxs-lookup"><span data-stu-id="d7df0-111">After upgrading an instance of the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] to [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] the SMK and DMK should be regenerated in order to upgrade the master keys to AES.</span></span> <span data-ttu-id="d7df0-112">Дополнительные сведения о повторном создании главного ключа базы данных см. в статьях [ALTER SERVICE MASTER KEY (Transact-SQL)](/sql/t-sql/statements/alter-service-master-key-transact-sql) и [ALTER MASTER KEY (Transact-SQL)](/sql/t-sql/statements/alter-master-key-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d7df0-112">For more information about regenerating the SMK, see [ALTER SERVICE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-service-master-key-transact-sql) and [ALTER MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-master-key-transact-sql).</span></span>  
  
## <a name="best-practice"></a><span data-ttu-id="d7df0-113">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="d7df0-113">Best Practice</span></span>  
 <span data-ttu-id="d7df0-114">Создайте резервную копию главного ключа службы и храните ее на безопасном автономном компьютере.</span><span class="sxs-lookup"><span data-stu-id="d7df0-114">Back up the Service Master Key and store the backed up copy in a secure, off-site location.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="d7df0-115">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="d7df0-115">Related Tasks</span></span>  
 [<span data-ttu-id="d7df0-116">BACKUP SERVICE MASTER KEY (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="d7df0-116">BACKUP SERVICE MASTER KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/backup-service-master-key-transact-sql)  
  
 [<span data-ttu-id="d7df0-117">RESTORE SERVICE MASTER KEY (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="d7df0-117">RESTORE SERVICE MASTER KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-service-master-key-transact-sql)  
  
 [<span data-ttu-id="d7df0-118">ALTER SERVICE MASTER KEY (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="d7df0-118">ALTER SERVICE MASTER KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-service-master-key-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="d7df0-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="d7df0-119">See Also</span></span>  
 [<span data-ttu-id="d7df0-120">Иерархия средств шифрования</span><span class="sxs-lookup"><span data-stu-id="d7df0-120">Encryption Hierarchy</span></span>](encryption-hierarchy.md)  
  
  
