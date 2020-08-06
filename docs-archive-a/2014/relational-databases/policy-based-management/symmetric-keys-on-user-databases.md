---
title: Симметричные ключи в пользовательских базах данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 3333ab5b-2518-4753-a0a8-57df5e5af74f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ca0fb62ccb32ce244e1087281997dcd9929df89c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657713"
---
# <a name="symmetric-keys-on-user-databases"></a><span data-ttu-id="53661-102">Симметричные ключи в пользовательских базах данных</span><span class="sxs-lookup"><span data-stu-id="53661-102">Symmetric Keys on User Databases</span></span>
  <span data-ttu-id="53661-103">Это правило проверяет, используют ли симметричные ключи длиной менее 128 бит алгоритмы шифрования RC2 или RC4.</span><span class="sxs-lookup"><span data-stu-id="53661-103">This rule checks whether keys that have a length of less than 128 bytes do not use the RC2 or RC4 encryption algorithm.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="53661-104">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="53661-104">Best Practices Recommendations</span></span>  
 <span data-ttu-id="53661-105">При создании симметричных ключей для шифрования данных используйте 128-битный алгоритм AES.</span><span class="sxs-lookup"><span data-stu-id="53661-105">Use AES 128 bit or larger to create symmetric keys for data encryption.</span></span> <span data-ttu-id="53661-106">Если алгоритм AES не поддерживается в операционной системе, следует применять алгоритм 3DES.</span><span class="sxs-lookup"><span data-stu-id="53661-106">If AES is not supported by your operating system, use 3DES.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="53661-107">Дополнительные сведения см. в разделе</span><span class="sxs-lookup"><span data-stu-id="53661-107">For More Information</span></span>  
 [<span data-ttu-id="53661-108">Выбор алгоритма шифрования</span><span class="sxs-lookup"><span data-stu-id="53661-108">Choose an Encryption Algorithm</span></span>](../security/encryption/choose-an-encryption-algorithm.md)  
  
## <a name="see-also"></a><span data-ttu-id="53661-109">См. также:</span><span class="sxs-lookup"><span data-stu-id="53661-109">See Also</span></span>  
 [<span data-ttu-id="53661-110">Наблюдение с помощью управления на основе политик и принудительное применение рекомендаций с помощью управления на основе политик</span><span class="sxs-lookup"><span data-stu-id="53661-110">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
