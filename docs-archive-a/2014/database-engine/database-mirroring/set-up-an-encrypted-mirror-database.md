---
title: Настройка зашифрованной зеркальной базы данных | Документы Майкрософт
ms.custom: ''
ms.date: 06/26/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- cryptography [SQL Server], database mirroring
- encryption [SQL Server], database mirroring
- database master key [SQL Server], database mirroring
- mirror database [SQL Server]
- database mirroring [SQL Server], security
ms.assetid: 7329a575-be29-46e0-abc6-1344db37920c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a5148411792f1ea881bba59e599252284575bbdf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733046"
---
# <a name="set-up-an-encrypted-mirror-database"></a><span data-ttu-id="eb489-102">Настройка зашифрованной зеркальной базы данных</span><span class="sxs-lookup"><span data-stu-id="eb489-102">Set Up an Encrypted Mirror Database</span></span>

<span data-ttu-id="eb489-103">Чтобы включить автоматическое шифрование главного ключа базы данных зеркальной базы данных, необходимо предоставить пароль, используемый для шифрования главного ключа экземпляра зеркального сервера.</span><span class="sxs-lookup"><span data-stu-id="eb489-103">To enable automatic decryption of the database master key of a mirror database, you must provide the password used to encrypt the master key to the mirror server instance.</span></span> [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] <span data-ttu-id="eb489-104">и более поздние версии включают в себя механизмы для передачи пароля.</span><span class="sxs-lookup"><span data-stu-id="eb489-104">and later versions include mechanisms to transfer the password.</span></span> <span data-ttu-id="eb489-105">Перед началом зеркального отображения базы данных необходимо создать учетные данные для главного ключа базы данных с помощью хранимой процедуры **sp_control_dbmasterkey_password** .</span><span class="sxs-lookup"><span data-stu-id="eb489-105">Use **sp_control_dbmasterkey_password** to create a credential for the database master key before you start database mirroring.</span></span> <span data-ttu-id="eb489-106">Необходимо повторить этот процесс для каждой базы данных, для которой будет создаваться зеркальное отображение.</span><span class="sxs-lookup"><span data-stu-id="eb489-106">You must repeat this process for every database that will be mirrored.</span></span> <span data-ttu-id="eb489-107">Дополнительные сведения см. в разделе [sp_control_dbmasterkey_password (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-control-dbmasterkey-password-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="eb489-107">For more information, see [sp_control_dbmasterkey_password &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-control-dbmasterkey-password-transact-sql).</span></span>
  
> [!CAUTION]  
>  <span data-ttu-id="eb489-108">Не включайте дешифрование базы данных отработки отказа, оно не должно быть для **sa** и другим серверам-участникам с обширными правами доступа.</span><span class="sxs-lookup"><span data-stu-id="eb489-108">Do not enable failover decryption of a database that must remain inaccessible to **sa** and other highly privileged server principals.</span></span> <span data-ttu-id="eb489-109">База данных может быть настроена таким образом, чтобы иерархия ее ключей не могла быть расшифрована главным ключом службы.</span><span class="sxs-lookup"><span data-stu-id="eb489-109">You can configure a database so that its key hierarchy cannot be decrypted by the service master key.</span></span> <span data-ttu-id="eb489-110">Эта возможность поддерживается для максимальной защиты баз данных, содержащих информацию, доступ к которой не может иметь **sa** или другие участники на уровне сервера с обширными правами доступа.</span><span class="sxs-lookup"><span data-stu-id="eb489-110">This option is supported as a defense-in-depth for databases that contain information that should not be accessible to **sa** or other highly privileged server principals.</span></span> <span data-ttu-id="eb489-111">Включение расшифровки отработки отказа для такой базы данных сводит на нет эту защиту, позволяя **sa** и другим привилегированным участникам на уровне сервера расшифровывать базу данных.</span><span class="sxs-lookup"><span data-stu-id="eb489-111">Enabling failover decryption of such a database removes this defense-in-depth, enabling **sa** and other highly privileged server principals to decrypt the database.</span></span>  


<!-- Note: We cannot append '?view=sql-server-2016' to these, even tho in theory we might want to. -->

## <a name="see-also"></a><span data-ttu-id="eb489-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="eb489-112">See Also</span></span>

[<span data-ttu-id="eb489-113">sp_control_dbmasterkey_password (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="eb489-113">sp_control_dbmasterkey_password &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-control-dbmasterkey-password-transact-sql)

[<span data-ttu-id="eb489-114">CREATE MASTER KEY (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="eb489-114">CREATE MASTER KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-master-key-transact-sql)

[<span data-ttu-id="eb489-115">ALTER MASTER KEY (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="eb489-115">ALTER MASTER KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-master-key-transact-sql)

[<span data-ttu-id="eb489-116">Иерархия средств шифрования</span><span class="sxs-lookup"><span data-stu-id="eb489-116">Encryption Hierarchy</span></span>](../../relational-databases/security/encryption/encryption-hierarchy.md)

[<span data-ttu-id="eb489-117">Настройка зеркального отображения базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="eb489-117">Setting Up Database Mirroring &#40;SQL Server&#41;</span></span>](database-mirroring-sql-server.md)

