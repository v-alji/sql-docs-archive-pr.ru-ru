---
title: Настройка ключей шифрования и управление ими (диспетчер конфигураций служб SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- encryption keys [Reporting Services]
- private keys [Reporting Services]
- cryptography [Reporting Services]
- symmetric keys [Reporting Services]
- encryption [Reporting Services]
- public keys [Reporting Services]
ms.assetid: 58e61636-88a2-4338-ae5f-3dd210aee887
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: afe9edff22c67b9b27c1fca88c9413f5a9ed98de
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751836"
---
# <a name="configure-and-manage-encryption-keys-ssrs-configuration-manager"></a><span data-ttu-id="95b5e-102">Настройка ключей шифрования и управление ими (диспетчер конфигурации служб SSRS)</span><span class="sxs-lookup"><span data-stu-id="95b5e-102">Configure and Manage Encryption Keys (SSRS Configuration Manager)</span></span>
  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="95b5e-103">пользуются ключами шифрования.</span><span class="sxs-lookup"><span data-stu-id="95b5e-103">uses encryption keys to secure credentials and connection information that is stored in a report server database.</span></span> <span data-ttu-id="95b5e-104">Для защиты конфиденциальных данных в службах [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]применяется сочетание открытого, закрытого и симметричного ключей.</span><span class="sxs-lookup"><span data-stu-id="95b5e-104">In [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], encryption is supported through a combination of public, private, and symmetric keys that are used to protect sensitive data.</span></span> <span data-ttu-id="95b5e-105">Симметричный ключ создается при инициализации сервера отчетов в момент его установки или настройки, и используется для шифрования конфиденциальных данных, хранящихся на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="95b5e-105">The symmetric key is created during report server initialization when you install or configure the report server, and it is used by the report server to encrypt sensitive data that is stored in the report server.</span></span> <span data-ttu-id="95b5e-106">Открытые и закрытые ключи создаются операционной системой, и используются для защиты симметричного ключа.</span><span class="sxs-lookup"><span data-stu-id="95b5e-106">Public and private keys are created by the operating system, and they are used to protect the symmetric key.</span></span> <span data-ttu-id="95b5e-107">Пара из открытого и закрытого ключей создается для каждого экземпляра, который сохраняет конфиденциальные данные в базе данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="95b5e-107">A public and private key pair is created for each report server instance that stores sensitive data in a report server database.</span></span>  
  
 <span data-ttu-id="95b5e-108">Управление ключами шифрования включает в себя создание резервной копии симметричного ключа и знание порядка восстановления, удаления и смены ключей.</span><span class="sxs-lookup"><span data-stu-id="95b5e-108">Managing the encryption keys consists of creating a backup copy of the symmetric key, and knowing when and how to restore, delete, or change the keys.</span></span> <span data-ttu-id="95b5e-109">При миграции установки сервера отчетов или настройки масштабного развертывания необходимо иметь резервную копию симметричного ключа, чтобы можно было применить ее к новой установке.</span><span class="sxs-lookup"><span data-stu-id="95b5e-109">If you migrate a report server installation or configure a scale-out deployment, you must have a backup copy of the symmetric key so that you can apply it to the new installation.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="95b5e-110">Рекомендацией по безопасности является периодическая смена ключа шифрования служб Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="95b5e-110">Periodically changing the Reporting Services encryption key is a security best practice.</span></span> <span data-ttu-id="95b5e-111">Рекомендуется менять ключ после каждого существенного обновления версии служб Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="95b5e-111">A recommended time to change the key is immediately following a major version upgrade of Reporting Services.</span></span> <span data-ttu-id="95b5e-112">Смена ключа после обновления способствует снижению до минимума дополнительного прерывания в обслуживании, которое может быть вызвано сменой ключа шифрования служб Reporting Services вне цикла обновления.</span><span class="sxs-lookup"><span data-stu-id="95b5e-112">Changing the key after an upgrade minimizes additional service interruption caused by changing the Reporting Services encryption key outside of the upgrade cycle.</span></span>  
  
 <span data-ttu-id="95b5e-113">Для управления симметричными ключами используется средство настройки служб Reporting Services или программа **rskeymgmt** .</span><span class="sxs-lookup"><span data-stu-id="95b5e-113">To manage symmetric keys, you can use the Reporting Services Configuration tool or the **rskeymgmt** utility.</span></span> <span data-ttu-id="95b5e-114">Средства, включенные в состав служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , предназначены только для управления симметричным ключом (управление закрытым и открытым ключами производит операционная система).</span><span class="sxs-lookup"><span data-stu-id="95b5e-114">The tools included in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] are used to manage the symmetric key only (the public and private keys are managed by the operating system).</span></span> <span data-ttu-id="95b5e-115">Как средство настройки служб Reporting Services, так и программа **rskeymgmt** поддерживают выполнение следующих задач:</span><span class="sxs-lookup"><span data-stu-id="95b5e-115">Both the Reporting Services Configuration tool and the **rskeymgmt** utility support the following tasks:</span></span>  
  
-   <span data-ttu-id="95b5e-116">Резервное копирование копии симметричного ключа для использования при восстановлении файлов установки сервера отчетов или в ходе запланированного переноса.</span><span class="sxs-lookup"><span data-stu-id="95b5e-116">Back up a copy of the symmetric key so that you can use it to recover a report server installation or as part of a planned migration.</span></span>  
  
-   <span data-ttu-id="95b5e-117">Восстановление сохраненного симметричного ключа в базе данных сервера отчетов, чтобы позволить новому экземпляру сервера отчетов обращаться к существующим данным, шифрование которых выполнил не он.</span><span class="sxs-lookup"><span data-stu-id="95b5e-117">Restore a previously saved symmetric key to a report server database, allowing a new report server instance to access existing data that it did not originally encrypt.</span></span>  
  
-   <span data-ttu-id="95b5e-118">Удаление зашифрованных данных из базы данных сервера отчетов в маловероятной ситуации, когда не удается обратиться к зашифрованным данным.</span><span class="sxs-lookup"><span data-stu-id="95b5e-118">Delete the encrypted data in a report server database in the unlikely event that you can no longer access encrypted data.</span></span>  
  
-   <span data-ttu-id="95b5e-119">Повторное создание симметричных ключей и повторное шифрование данных в маловероятной ситуации, когда симметричный ключ становится известен посторонним.</span><span class="sxs-lookup"><span data-stu-id="95b5e-119">Re-create symmetric keys and re-encrypt data in the unlikely event that the symmetric key is compromised.</span></span> <span data-ttu-id="95b5e-120">Для повышения безопасности следует периодически повторно создавать симметричный ключ (например, раз в несколько месяцев) для защиты базы данных сервера отчетов от электронных атак с целью расшифровки ключа.</span><span class="sxs-lookup"><span data-stu-id="95b5e-120">As a security best practice, you should recreate the symmetric key periodically (for example, every few months) to protect the report server database from cyber attacks that attempt to decipher the key.</span></span>  
  
-   <span data-ttu-id="95b5e-121">Добавление или удаление экземпляра сервера отчетов из масштабного развертывания, когда несколько серверов отчетов используют одну базу данных сервера отчетов и симметричный ключ, допускающий двустороннее шифрование для этой базы данных.</span><span class="sxs-lookup"><span data-stu-id="95b5e-121">Add or remove a report server instance from a report server scale-out deployment where multiple report servers share both a single report server database and the symmetric key that provides reversible encryption for that database.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="95b5e-122">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="95b5e-122">In This Section</span></span>  
 [<span data-ttu-id="95b5e-123">Инициализация сервера отчетов &#40;диспетчер конфигурации служб SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="95b5e-123">Initialize a Report Server &#40;SSRS Configuration Manager&#41;</span></span>](ssrs-encryption-keys-initialize-a-report-server.md)  
 <span data-ttu-id="95b5e-124">Объясняет, как создавать ключи шифрования.</span><span class="sxs-lookup"><span data-stu-id="95b5e-124">Explains how encryption keys are created.</span></span>  
  
 [<span data-ttu-id="95b5e-125">Резервное копирование и восстановление ключей шифрования служб Reporting Services</span><span class="sxs-lookup"><span data-stu-id="95b5e-125">Back Up and Restore Reporting Services Encryption Keys</span></span>](ssrs-encryption-keys-back-up-and-restore-encryption-keys.md)  
 <span data-ttu-id="95b5e-126">Объясняет, как проводить резервное копирование ключей шифрования и восстанавливать их при восстановлении или перемещении файлов установки сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="95b5e-126">Explains how to back up encryption keys and restore them to recover or migrate a report server installation.</span></span>  
  
 [<span data-ttu-id="95b5e-127">Хранение зашифрованных данных сервера отчетов &#40;диспетчер конфигурации служб SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="95b5e-127">Store Encrypted Report Server Data &#40;SSRS Configuration Manager&#41;</span></span>](ssrs-encryption-keys-store-encrypted-report-server-data.md)  
 <span data-ttu-id="95b5e-128">Описывает шифрование на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="95b5e-128">Describes encryption on a report server.</span></span>  
  
 [<span data-ttu-id="95b5e-129">Удаление и повторное создание ключей шифрования (диспетчер конфигурации служб SSRS)</span><span class="sxs-lookup"><span data-stu-id="95b5e-129">Delete and Re-create Encryption Keys  &#40;SSRS Configuration Manager&#41;</span></span>](ssrs-encryption-keys-delete-and-re-create-encryption-keys.md)  
 <span data-ttu-id="95b5e-130">Объясняет, как заменить симметричный ключ новой версией, а также как начать сначала, если симметричные ключи невозможно проверить.</span><span class="sxs-lookup"><span data-stu-id="95b5e-130">Explains how you can replace a symmetric key with a new version, and how to start over if symmetric keys cannot be validated.</span></span>  
  
 [<span data-ttu-id="95b5e-131">Добавление и удаление ключей шифрования для масштабного развертывания (диспетчер конфигурации служб SSRS)</span><span class="sxs-lookup"><span data-stu-id="95b5e-131">Add and Remove Encryption Keys for Scale-Out Deployment &#40;SSRS Configuration Manager&#41;</span></span>](add-and-remove-encryption-keys-for-scale-out-deployment.md)  
 <span data-ttu-id="95b5e-132">Объясняет, как добавить или удалить ключи шифрования для управления списком серверов отчетов, входящих в масштабное развертывание.</span><span class="sxs-lookup"><span data-stu-id="95b5e-132">Explains how to add and remove encryption keys to control which report servers are part of a scale-out deployment.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95b5e-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="95b5e-133">See Also</span></span>  
 [<span data-ttu-id="95b5e-134">Хранение зашифрованных данных сервера отчетов &#40;диспетчер конфигурации служб SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="95b5e-134">Store Encrypted Report Server Data &#40;SSRS Configuration Manager&#41;</span></span>](ssrs-encryption-keys-store-encrypted-report-server-data.md)  
  
  
