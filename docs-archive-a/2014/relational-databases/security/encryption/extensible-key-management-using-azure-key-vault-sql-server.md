---
title: Расширенное управление ключами с помощью Azure Key Vault (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- EKM, with key vault
- TDE, EKM and key vault
- Extensible Key Management with key vault
- Key Management with key vault
- Transparent Data Encryption, using EKM and key vault
ms.assetid: 3efdc48a-8064-4ea6-a828-3fbf758ef97c
author: jaszymas
ms.author: jaszymas
ms.openlocfilehash: 0e4bbc4f0c371c927988e6b91fdbf47307ad9d3f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752071"
---
# <a name="extensible-key-management-using-azure-key-vault-sql-server"></a><span data-ttu-id="c39c4-102">Расширенное управление ключами с помощью хранилища ключей Azure (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="c39c4-102">Extensible Key Management Using Azure Key Vault (SQL Server)</span></span>
  <span data-ttu-id="c39c4-103">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]Соединитель для [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Azure Key Vault позволяет [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] использовать шифрование для использования Azure Key Vault службы в качестве [расширенного управления КЛЮЧами &#40;поставщика расширенных ключей&#41;](extensible-key-management-ekm.md) для защиты ключей шифрования.</span><span class="sxs-lookup"><span data-stu-id="c39c4-103">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Connector for [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Azure Key Vault enables [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] encryption to leverage the Azure Key Vault service as an [Extensible Key Management &#40;EKM&#41;](extensible-key-management-ekm.md) provider to protect its encryption keys.</span></span>

 <span data-ttu-id="c39c4-104">Разделы данной темы</span><span class="sxs-lookup"><span data-stu-id="c39c4-104">Included in this topic:</span></span>

-   [<span data-ttu-id="c39c4-105">Использование расширенного управления ключами</span><span class="sxs-lookup"><span data-stu-id="c39c4-105">Uses of EKM</span></span>](#Uses)

-   [<span data-ttu-id="c39c4-106">Шаг 1. Настройка хранилища ключей для использования в SQL Server</span><span class="sxs-lookup"><span data-stu-id="c39c4-106">Step 1: Setting up the Key Vault for use by SQL Server</span></span>](#Step1)

-   [<span data-ttu-id="c39c4-107">Шаг 2. Установка соединителя SQL Server</span><span class="sxs-lookup"><span data-stu-id="c39c4-107">Step 2: Installing the SQL Server Connector</span></span>](#Step2)

-   [<span data-ttu-id="c39c4-108">Шаг 3. Настройка SQL Server для использования поставщика EKM для хранилища ключей</span><span class="sxs-lookup"><span data-stu-id="c39c4-108">Step 3: Configure SQL Server to use an EKM provider for the Key Vault</span></span>](#Step3)

-   [<span data-ttu-id="c39c4-109">Пример А. Прозрачное шифрование данных с помощью асимметричного ключа из хранилища ключей</span><span class="sxs-lookup"><span data-stu-id="c39c4-109">Example A: Transparent Data Encryption by Using an Asymmetric Key from the Key Vault</span></span>](#ExampleA)

-   [<span data-ttu-id="c39c4-110">Пример Б. Шифрование резервных копий с помощью асимметричного ключа из хранилища ключей</span><span class="sxs-lookup"><span data-stu-id="c39c4-110">Example B: Encrypting Backups by Using an Asymmetric Key from the Key Vault</span></span>](#ExampleB)

-   [<span data-ttu-id="c39c4-111">Пример В. Шифрование данных на уровне столбца с помощью асимметричного ключа из хранилища ключей</span><span class="sxs-lookup"><span data-stu-id="c39c4-111">Example C: Column Level Encryption by Using an Asymmetric Key from the Key Vault</span></span>](#ExampleC)

##  <a name="uses-of-ekm"></a><a name="Uses"></a><span data-ttu-id="c39c4-112">Использование расширенного управления ключами</span><span class="sxs-lookup"><span data-stu-id="c39c4-112">Uses of EKM</span></span>
 <span data-ttu-id="c39c4-113">Организация может использовать шифрование [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] для защиты конфиденциальных данных.</span><span class="sxs-lookup"><span data-stu-id="c39c4-113">An organization can use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] encryption to protect sensitive data.</span></span> [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="c39c4-114">Шифрование включает [прозрачное шифрование данных &#40;TDE&#41;](transparent-data-encryption.md), [Шифрование на уровне столбцов](/sql/t-sql/functions/cryptographic-functions-transact-sql) (CLE) и [Шифрование резервных копий](../../backup-restore/backup-encryption.md).</span><span class="sxs-lookup"><span data-stu-id="c39c4-114">encryption includes [Transparent Data Encryption &#40;TDE&#41;](transparent-data-encryption.md), [Column Level Encryption](/sql/t-sql/functions/cryptographic-functions-transact-sql) (CLE), and [Backup Encryption](../../backup-restore/backup-encryption.md).</span></span> <span data-ttu-id="c39c4-115">Во всех этих случаях данные шифруются с помощью симметричного ключа шифрования.</span><span class="sxs-lookup"><span data-stu-id="c39c4-115">In all of these cases the data is encrypted using a symmetric data encryption key.</span></span> <span data-ttu-id="c39c4-116">Симметричный ключ шифрования затем шифруется иерархией ключей, хранящихся в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c39c4-116">The symmetric data encryption key is further protected by encrypting it with a hierarchy of keys stored in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c39c4-117">Или же архитектура поставщика EKM использует [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] для защиты ключей шифрования данных с помощью асимметричного ключа, который хранится вне [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] во внешнем поставщике служб шифрования.</span><span class="sxs-lookup"><span data-stu-id="c39c4-117">Alternatively, the EKM provider architecture enables [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to protect the data encryption keys by using an asymmetric key stored outside of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in an external cryptographic provider.</span></span> <span data-ttu-id="c39c4-118">Архитектура поставщика EKM добавляет дополнительный уровень безопасности и позволяет организациям разделить управление ключами и данными.</span><span class="sxs-lookup"><span data-stu-id="c39c4-118">Using EKM provider architecture adds an additional layer of security and allows organizations to separate the management of keys and data.</span></span>

 <span data-ttu-id="c39c4-119">Соединитель [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] для хранилища ключей Azure позволяет [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] использовать масштабируемую, высокопроизводительную и высокодоступную службу хранилища ключей в качестве поставщика расширенного управления ключами для защиты ключа шифрования.</span><span class="sxs-lookup"><span data-stu-id="c39c4-119">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Connector for Azure Key Vault lets [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] leverage the scalable, high performance, and highly available key vault service as an EKM provider for encryption key protection.</span></span> <span data-ttu-id="c39c4-120">Службу хранилища ключей можно использовать с установками [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] на виртуальных машинах [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Azure и для локальных серверов.</span><span class="sxs-lookup"><span data-stu-id="c39c4-120">The key vault service can be used with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] installations on [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Azure Virtual Machines and for on-premises servers.</span></span> <span data-ttu-id="c39c4-121">Служба хранилища ключей также предоставляет возможность использовать жестко контролируемые и отслеживаемые аппаратные модули безопасности (HSM) для обеспечения более высокого уровня защиты асимметричных ключей шифрования.</span><span class="sxs-lookup"><span data-stu-id="c39c4-121">The key vault service also provides the option to use tightly controlled and monitored Hardware Security Modules (HSMs) for a higher level of protection for asymmetric encryption keys.</span></span> <span data-ttu-id="c39c4-122">Дополнительные сведения о хранилище ключей см. в статье [Хранилище ключей Azure](https://go.microsoft.com/fwlink/?LinkId=521401).</span><span class="sxs-lookup"><span data-stu-id="c39c4-122">For more information about the key vault, see [Azure Key Vault](https://go.microsoft.com/fwlink/?LinkId=521401).</span></span>

 <span data-ttu-id="c39c4-123">На следующем изображении представлен поток процесса расширенного управления ключами с использованием хранилища ключей.</span><span class="sxs-lookup"><span data-stu-id="c39c4-123">The following image summarizes the process flow of EKM using the key vault.</span></span> <span data-ttu-id="c39c4-124">Номера шагов процесса на изображении не обязательно соответствуют номерам шагов установки, указанным после изображения.</span><span class="sxs-lookup"><span data-stu-id="c39c4-124">The process step numbers in the image are not meant to match the setup step numbers that follow the image.</span></span>

 <span data-ttu-id="c39c4-125">![Расширенное управление ключами SQL Server с использованием Azure Key Vault](../../../database-engine/media/ekm-using-azure-key-vault.png "Расширенное управление ключами SQL Server с использованием Azure Key Vault")</span><span class="sxs-lookup"><span data-stu-id="c39c4-125">![SQL Server EKM using the Azure Key Vault](../../../database-engine/media/ekm-using-azure-key-vault.png "SQL Server EKM using the Azure Key Vault")</span></span>

##  <a name="step-1-set-up-the-key-vault-for-use-by-sql-server"></a><a name="Step1"></a><span data-ttu-id="c39c4-126">Шаг 1. Настройка Key Vault для использования SQL Server</span><span class="sxs-lookup"><span data-stu-id="c39c4-126">Step 1: Set up the Key Vault for use by SQL Server</span></span>
 <span data-ttu-id="c39c4-127">Выполните следующие действия, чтобы настроить хранилище ключей для использования с [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)] в целях защиты ключа шифрования.</span><span class="sxs-lookup"><span data-stu-id="c39c4-127">Use the following steps to set up a key vault for use with the [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)] for encryption key protection.</span></span> <span data-ttu-id="c39c4-128">Организация может уже использовать хранилище.</span><span class="sxs-lookup"><span data-stu-id="c39c4-128">A vault may already be in use for the organization.</span></span> <span data-ttu-id="c39c4-129">Если хранилище не существует, администратор Azure в организации, назначенный для управления ключами шифрования, может создать хранилище, создать асимметричный ключ в хранилище и затем авторизовать [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] для использования ключа.</span><span class="sxs-lookup"><span data-stu-id="c39c4-129">When a vault does not exist, the Azure Administrator in your organization that is designated to manage encryption keys can create a vault, generate an asymmetric key in the vault, and then authorize [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to use the key.</span></span> <span data-ttu-id="c39c4-130">Ознакомьтесь со службой хранилища ключей, изучив статью [Приступая к работе с хранилищем ключей Azure](https://go.microsoft.com/fwlink/?LinkId=521402), и справочником по [командлетам PowerShell для работы с хранилищем ключей Azure](https://docs.microsoft.com/powershell/module/azurerm.keyvault) .</span><span class="sxs-lookup"><span data-stu-id="c39c4-130">To familiarize yourself with the key vault service review [Get Started with Azure Key Vault](https://go.microsoft.com/fwlink/?LinkId=521402), and the PowerShell [Azure Key Vault Cmdlets](https://docs.microsoft.com/powershell/module/azurerm.keyvault) reference.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="c39c4-131">Если у вас несколько подписок Azure, вы должны использовать ту подписку, которая содержит [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c39c4-131">If you have multiple Azure subscriptions, you must use the subscription that contains [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>

1.  <span data-ttu-id="c39c4-132">**Создание хранилища.** Создайте хранилище, следуя инструкциям в разделе **Создание хранилища ключей** статьи [Приступая к работе с хранилищем ключей Azure](https://go.microsoft.com/fwlink/?LinkId=521402).</span><span class="sxs-lookup"><span data-stu-id="c39c4-132">**Create a vault:** Create a vault by using the instructions in the **Create a key vault** section of [Get Started with Azure Key Vault](https://go.microsoft.com/fwlink/?LinkId=521402).</span></span> <span data-ttu-id="c39c4-133">Запишите имя хранилища.</span><span class="sxs-lookup"><span data-stu-id="c39c4-133">Record the name of the vault.</span></span> <span data-ttu-id="c39c4-134">В этом разделе используется имя **ContosoKeyVault** .</span><span class="sxs-lookup"><span data-stu-id="c39c4-134">This topic uses **ContosoKeyVault** as the key vault name.</span></span>

2.  <span data-ttu-id="c39c4-135">**Создание асимметричного ключа в хранилище.** Асимметричный ключ в хранилище ключей используется для защиты ключей шифрования [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c39c4-135">**Generate an asymmetric key in the vault:** The asymmetric key in the key vault is used to protect [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] encryption keys.</span></span> <span data-ttu-id="c39c4-136">Только открытая часть асимметричного ключа покидает хранилище, частная же область никогда не экспортируется.</span><span class="sxs-lookup"><span data-stu-id="c39c4-136">Only the public portion of the asymmetric key ever leaves the vault, the private portion is never exported by the vault.</span></span> <span data-ttu-id="c39c4-137">Все криптографические операции, использующие асимметричный ключ, делегируются в хранилище ключей Azure и защищаются системой безопасности хранилища.</span><span class="sxs-lookup"><span data-stu-id="c39c4-137">All cryptographic operations using the asymmetric key are delegated to the Azure Key Vault, and are protected by the key vault security.</span></span>

     <span data-ttu-id="c39c4-138">Существует несколько способов создания асимметричного ключа и сохранения его в хранилище.</span><span class="sxs-lookup"><span data-stu-id="c39c4-138">There are several ways that you can generate an asymmetric key and store it in the vault.</span></span> <span data-ttu-id="c39c4-139">Можно создать ключ извне и импортировать его в хранилище в виде PFX-файла.</span><span class="sxs-lookup"><span data-stu-id="c39c4-139">You can externally generate a key, and import the key into the vault as a .pfx file.</span></span> <span data-ttu-id="c39c4-140">Или можно создать ключ непосредственно в хранилище с помощью API хранилища ключей.</span><span class="sxs-lookup"><span data-stu-id="c39c4-140">Or create the key directly in the vault by using the key vault APIs.</span></span>

     <span data-ttu-id="c39c4-141">Соединитель [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] использует 2048-разрядные асимметричные ключи RSA, а имя ключа может содержать только символы "a — z", "A — Z", "0—9" и "-".</span><span class="sxs-lookup"><span data-stu-id="c39c4-141">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Connector requires the asymmetric keys to be 2048-bit RSA, and the key name can only use the characters "a-z", "A-Z", "0-9", and "-".</span></span> <span data-ttu-id="c39c4-142">В этом документе имя асимметричного ключа — **ContosoMasterKey**.</span><span class="sxs-lookup"><span data-stu-id="c39c4-142">In this document the name of the asymmetric key is referred to as **ContosoMasterKey**.</span></span> <span data-ttu-id="c39c4-143">Замените его на уникальное имя ключа.</span><span class="sxs-lookup"><span data-stu-id="c39c4-143">Replace this with the unique name you use for the key.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="c39c4-144">Импорт асимметричного ключа настоятельно рекомендуется для рабочих сценариев, так как это позволяет администратору передать ключ в систему переноса ключей.</span><span class="sxs-lookup"><span data-stu-id="c39c4-144">Importing the asymmetric key is highly recommended for production scenarios because it allows the administrator to escrow the key in a key escrow system.</span></span> <span data-ttu-id="c39c4-145">Если в хранилище создается асимметричный ключ, он не может быть передан, так как закрытый ключ не может покидать хранилище.</span><span class="sxs-lookup"><span data-stu-id="c39c4-145">If the asymmetric key is created in the vault, it cannot be escrowed because the private key can never leave the vault.</span></span> <span data-ttu-id="c39c4-146">Ключи, используемые для защиты важных данных, должны быть перенесены.</span><span class="sxs-lookup"><span data-stu-id="c39c4-146">Keys used to protect critical data should be escrowed.</span></span> <span data-ttu-id="c39c4-147">Потеря асимметричного ключа приведет к невозможности восстановить данные.</span><span class="sxs-lookup"><span data-stu-id="c39c4-147">The loss of an asymmetric key will result in permanently unrecoverable data.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="c39c4-148">Хранилище ключей поддерживает несколько версий ключа с одним именем.</span><span class="sxs-lookup"><span data-stu-id="c39c4-148">The key vault supports multiple versions of the same named key.</span></span> <span data-ttu-id="c39c4-149">Для ключей, используемых соединителем [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , не должна применяться система управления версиями или откат.</span><span class="sxs-lookup"><span data-stu-id="c39c4-149">Keys to be used by [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Connector should not be versioned or rolled.</span></span> <span data-ttu-id="c39c4-150">Если администратору требуется откатить ключ, используемый для шифрования [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , следует создать ключ с другим именем в хранилище и использовать его для шифрования ключа шифрования базы данных.</span><span class="sxs-lookup"><span data-stu-id="c39c4-150">If the administrator wants to roll the key used for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] encryption, a new key with a different name should be created in the vault and used to encrypt the DEK.</span></span>

     <span data-ttu-id="c39c4-151">Дополнительные сведения о том, как импортировать ключ в хранилище ключей или создать ключ в хранилище ключей (не рекомендуется для рабочей среды), см. в разделе **Добавление ключа или секретного кода в хранилище ключей** статьи [Приступая к работе с хранилищем ключей Azure](https://go.microsoft.com/fwlink/?LinkId=521402).</span><span class="sxs-lookup"><span data-stu-id="c39c4-151">For more information on how to import a key into the key vault or to create a key in the key vault (not recommended for a production environment), see the **Add a key or secret to the key vault** section in [Get Started with Azure Key Vault](https://go.microsoft.com/fwlink/?LinkId=521402).</span></span>

3.  <span data-ttu-id="c39c4-152">**Получение субъектов-служб Azure Active Directory для SQL Server.** Когда организация регистрируется в облачной службе Майкрософт, она получает Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c39c4-152">**Get Azure Active Directory Service Principals to use for SQL Server:** When the organization signs up for a Microsoft cloud service, it gets an Azure Active Directory.</span></span> <span data-ttu-id="c39c4-153">Создайте **субъекты-службы** в Azure Active Directory для [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , которые будут использоваться (для проверки подлинности в Azure Active Directory) при доступе к хранилищу ключей.</span><span class="sxs-lookup"><span data-stu-id="c39c4-153">Create **Service Principals** in the Azure Active Directory for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to use (to authenticate itself to Azure Active Directory) while accessing the key vault.</span></span>

    -   <span data-ttu-id="c39c4-154">Один **субъект-служба** понадобится администратору [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] для доступа к хранилищу при настройке [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] для шифрования.</span><span class="sxs-lookup"><span data-stu-id="c39c4-154">One **Service Principal** will be needed by a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] administrator to access the vault while configuring [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to use encryption.</span></span>

    -   <span data-ttu-id="c39c4-155">Другой **субъект-служба** понадобится [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)] для доступа к хранилищу для распаковки ключей, используемых при шифровании [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c39c4-155">Another **Service Principal** will be needed by the [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)] to access the vault for unwrapping keys used in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] encryption.</span></span>

     <span data-ttu-id="c39c4-156">Дополнительные сведения о регистрации приложения и создании субъекта-службы см. в разделе **Регистрация приложения в Azure Active Directory** статьи [Приступая к работе с хранилищем ключей Azure](https://go.microsoft.com/fwlink/?LinkId=521402).</span><span class="sxs-lookup"><span data-stu-id="c39c4-156">For more information about how to register an application and generate a service principal, see the **Register an Application with Azure Active Directory** section in [Get Started with Azure Key Vault](https://go.microsoft.com/fwlink/?LinkId=521402).</span></span> <span data-ttu-id="c39c4-157">Процесс регистрации возвращает **идентификатор приложения** (также известный как **идентификатор клиента**) и **ключ проверки подлинности** (также известный как **секрет**) для каждого **субъекта-службы**Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c39c4-157">The registration process returns an **Application ID** (also known as a **CLIENT ID**) and a **Authentication Key** (also known as a **Secret**) for each Azure Active Directory **Service Principal**.</span></span> <span data-ttu-id="c39c4-158">При использовании в `CREATE CREDENTIAL` инструкции дефис должен быть удален из **идентификатора клиента**.</span><span class="sxs-lookup"><span data-stu-id="c39c4-158">When used in the `CREATE CREDENTIAL` statement, the hyphen must be removed from the **CLIENT ID**.</span></span> <span data-ttu-id="c39c4-159">Запишите их для использования в следующих скриптах.</span><span class="sxs-lookup"><span data-stu-id="c39c4-159">Record these for use in the scripts below:</span></span>

    -   <span data-ttu-id="c39c4-160">**Субъект-служба** для имени входа **sysadmin** : **CLIENTID_sysadmin_login** и **SECRET_sysadmin_login**</span><span class="sxs-lookup"><span data-stu-id="c39c4-160">**Service Principal** for a **sysadmin** login: **CLIENTID_sysadmin_login** and **SECRET_sysadmin_login**</span></span>

    -   <span data-ttu-id="c39c4-161">**Субъект-служба** для [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)]: **CLIENTID_DBEngine** и **SECRET_DBEngine**.</span><span class="sxs-lookup"><span data-stu-id="c39c4-161">**Service Principal** for the [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)]: **CLIENTID_DBEngine** and **SECRET_DBEngine**.</span></span>

4.  <span data-ttu-id="c39c4-162">**Предоставление субъекту-службе разрешений для доступа к хранилищу ключей.** Субъектам-службам **CLIENTID_sysadmin_login** и **CLIENTID_DBEngine** необходимы разрешения **get**, **list**, **wrapKey**, и **unwrapKey** в хранилище ключей.</span><span class="sxs-lookup"><span data-stu-id="c39c4-162">**Grant Permission for the Service Principals to access the Key Vault:** Both the **CLIENTID_sysadmin_login** and **CLIENTID_DBEngineService Principals** require the **get**, **list**, **wrapKey**, and **unwrapKey** permissions in the key vault.</span></span> <span data-ttu-id="c39c4-163">Если вы планируете создать ключи с помощью [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , вам также необходимо предоставить разрешение **create** в хранилище ключей.</span><span class="sxs-lookup"><span data-stu-id="c39c4-163">If you intend to create keys through [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] you also need to grant the **create** permission in key vault.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="c39c4-164">У пользователей должны быть по крайней мере операции **wrapKey** и **unwrapKey** для хранилища ключей.</span><span class="sxs-lookup"><span data-stu-id="c39c4-164">Users must have at least the **wrapKey** and **unwrapKey** operations for the key vault.</span></span>

     <span data-ttu-id="c39c4-165">Дополнительные сведения о предоставлении разрешений в хранилище см. в разделе **Авторизация приложения для использования ключа или секрета** статьи [Приступая к работе с хранилищем ключей Azure](https://go.microsoft.com/fwlink/?LinkId=521402).</span><span class="sxs-lookup"><span data-stu-id="c39c4-165">For more information about granting permissions to the vault, see the **Authorize the application to use the key or secret** section in [Get Started with Azure Key Vault](https://go.microsoft.com/fwlink/?LinkId=521402).</span></span>

     <span data-ttu-id="c39c4-166">Ссылки на документацию по хранилищу ключей Azure</span><span class="sxs-lookup"><span data-stu-id="c39c4-166">Links to Azure Key Vault documentation</span></span>

    -   [<span data-ttu-id="c39c4-167">Что такое хранилище ключей Azure?</span><span class="sxs-lookup"><span data-stu-id="c39c4-167">What is Azure Key Vault?</span></span>](https://go.microsoft.com/fwlink/?LinkId=521401)

    -   [<span data-ttu-id="c39c4-168">Приступая к работе с хранилищем ключей Azure</span><span class="sxs-lookup"><span data-stu-id="c39c4-168">Get Started with Azure Key Vault</span></span>](https://go.microsoft.com/fwlink/?LinkId=521402)

    -   <span data-ttu-id="c39c4-169">Справочник по [командлетам PowerShell для работы с хранилищем ключей Azure](https://docs.microsoft.com/powershell/module/azurerm.keyvault)</span><span class="sxs-lookup"><span data-stu-id="c39c4-169">PowerShell [Azure Key Vault Cmdlets](https://docs.microsoft.com/powershell/module/azurerm.keyvault) reference</span></span>

##  <a name="step-2-install-the-sql-server-connector"></a><a name="Step2"></a><span data-ttu-id="c39c4-170">Шаг 2. Установка соединитель SQL Server</span><span class="sxs-lookup"><span data-stu-id="c39c4-170">Step 2: Install the SQL Server Connector</span></span>
 <span data-ttu-id="c39c4-171">Соединитель [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] будет загружен и установлен администратором компьютера [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c39c4-171">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Connector is downloaded and installed by the administrator of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] computer.</span></span> <span data-ttu-id="c39c4-172">Соединитель [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] можно загрузить из [Центра загрузки Майкрософт](https://go.microsoft.com/fwlink/p/?LinkId=521700).</span><span class="sxs-lookup"><span data-stu-id="c39c4-172">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Connector is available as a download from the [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=521700).</span></span>  <span data-ttu-id="c39c4-173">Выполните поиск **соединителя SQL Server для хранилища ключей Microsoft Azure**, просмотрите подробные сведения, требования к системе и инструкции по установке, загрузите соединитель и начните установку с помощью команды **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="c39c4-173">Search for **SQL Server Connector for Microsoft Azure Key Vault**, review the details, system requirements and install instructions and choose to download the connector and start the installation using **Run**.</span></span> <span data-ttu-id="c39c4-174">Прочитайте лицензионное соглашение, примите его условия и продолжайте.</span><span class="sxs-lookup"><span data-stu-id="c39c4-174">Review the license and accept the license and continue.</span></span>

 <span data-ttu-id="c39c4-175">По умолчанию соединитель устанавливается в папку **C:\Program Files\SQL Server Connector для Microsoft Azure Key Vault**.</span><span class="sxs-lookup"><span data-stu-id="c39c4-175">By default the connector is installed at **C:\Program Files\SQL Server Connector for Microsoft Azure Key Vault**.</span></span> <span data-ttu-id="c39c4-176">Эту папку можно изменить во время установки.</span><span class="sxs-lookup"><span data-stu-id="c39c4-176">This location can be changed during setup.</span></span> <span data-ttu-id="c39c4-177">(В этом случае измените и следующие скрипты.)</span><span class="sxs-lookup"><span data-stu-id="c39c4-177">(If changed, adjust the scripts below.)</span></span>

 <span data-ttu-id="c39c4-178">После завершения установки на компьютер установлены следующие компоненты.</span><span class="sxs-lookup"><span data-stu-id="c39c4-178">On completing the install, the following are installed on the machine:</span></span>

-   <span data-ttu-id="c39c4-179">**Microsoft.AzureKeyVaultService.EKM.dll**: это DLL-библиотека поставщика расширенного управления ключами, которую необходимо зарегистрировать в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] с помощью инструкции CREATE CRYPTOGRAPHIC PROVIDER.</span><span class="sxs-lookup"><span data-stu-id="c39c4-179">**Microsoft.AzureKeyVaultService.EKM.dll**: This is the cryptographic EKM provider DLL that needs to be registered with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using the CREATE CRYPTOGRAPHIC PROVIDER statement.</span></span>

-   <span data-ttu-id="c39c4-180">**Соединитель SQL Server для хранилища ключей Azure**— это служба Windows, которая позволяет поставщику EKM взаимодействовать с хранилищем ключей.</span><span class="sxs-lookup"><span data-stu-id="c39c4-180">**Azure Key Vault SQL Server Connector**: This is a Windows service that enables the cryptographic EKM provider to communicate with the key vault.</span></span>

 <span data-ttu-id="c39c4-181">Установка соединителя [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] также позволяет при необходимости загрузить примеры скриптов для шифрования [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c39c4-181">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Connector installation also allows you to optionally download sample scripts for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] encryption.</span></span>

##  <a name="step-3-configure-sql-server-to-use-an-ekm-provider-for-the-key-vault"></a><a name="Step3"></a><span data-ttu-id="c39c4-182">Шаг 3. Настройка SQL Server для использования поставщика расширенного управления ключами для Key Vault</span><span class="sxs-lookup"><span data-stu-id="c39c4-182">Step 3: Configure SQL Server to use an EKM provider for the Key Vault</span></span>

###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c39c4-183">Permissions</span><span class="sxs-lookup"><span data-stu-id="c39c4-183">Permissions</span></span>
 <span data-ttu-id="c39c4-184">Для завершения всего процесса требуется разрешение CONTROL SERVER или членство в предопределенной роли сервера **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="c39c4-184">To complete this entire process requires CONTROL SERVER permission or membership in the **sysadmin** fixed server role.</span></span> <span data-ttu-id="c39c4-185">Для определенных действий необходимы следующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="c39c4-185">Specific actions require the following permissions:</span></span>

-   <span data-ttu-id="c39c4-186">Для создания поставщика служб шифрования требуется разрешение CONTROL SERVER или членство в предопределенной роли сервера **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="c39c4-186">To create a cryptographic provider, requires CONTROL SERVER permission or membership in the **sysadmin** fixed server role.</span></span>

-   <span data-ttu-id="c39c4-187">Для изменения параметра конфигурации и выполнения инструкции RECONFIGURE должно быть предоставлено разрешение ALTER SETTINGS на уровне сервера.</span><span class="sxs-lookup"><span data-stu-id="c39c4-187">To change a configuration option and run the RECONFIGURE statement, you must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="c39c4-188">Разрешение ALTER SETTINGS неявным образом предоставлено предопределенным ролям сервера **sysadmin** и **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="c39c4-188">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>

-   <span data-ttu-id="c39c4-189">Для создания учетных данных требуется разрешение ALTER ANY CREDENTIAL.</span><span class="sxs-lookup"><span data-stu-id="c39c4-189">To create a credential, requires ALTER ANY CREDENTIAL permission.</span></span>

-   <span data-ttu-id="c39c4-190">Для добавления учетных данных необходимо разрешение ALTER ANY LOGIN.</span><span class="sxs-lookup"><span data-stu-id="c39c4-190">To add a credential to a login, requires ALTER ANY LOGIN permission.</span></span>

-   <span data-ttu-id="c39c4-191">Для создания асимметричного ключа требуется разрешение CREATE ASYMMETRIC KEY.</span><span class="sxs-lookup"><span data-stu-id="c39c4-191">To create an asymmetric key, requires CREATE ASYMMETRIC KEY permission.</span></span>

###  <a name="to-configure-sql-server-to-use-a-cryptographic-provider"></a><a name="TsqlProcedure"></a><span data-ttu-id="c39c4-192">Настройка SQL Server для использования поставщика служб шифрования</span><span class="sxs-lookup"><span data-stu-id="c39c4-192">To configure SQL Server to use a cryptographic provider</span></span>

1.  <span data-ttu-id="c39c4-193">Настройте [!INCLUDE[ssDE](../../../includes/ssde-md.md)] для использования EKM и зарегистрируйте (создайте) поставщика служб шифрования с помощью [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c39c4-193">Configure the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] to use EKM, and register (create) the cryptographic provider with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>

    ```sql
    -- Enable advanced options.
    USE master;
    GO

    sp_configure 'show advanced options', 1 ;
    GO
    RECONFIGURE ;
    GO
    -- Enable EKM provider
    sp_configure 'EKM provider enabled', 1 ;
    GO
    RECONFIGURE ;
    GO

    -- Create a cryptographic provider, using the SQL Server Connector
    -- which is an EKM provider for the Azure Key Vault. This example uses 
    -- the name AzureKeyVault_EKM_Prov.

    CREATE CRYPTOGRAPHIC PROVIDER AzureKeyVault_EKM_Prov 
    FROM FILE = 'C:\Program Files\SQL Server Connector for Microsoft Azure Key Vault\Microsoft.AzureKeyVaultService.EKM.dll';
    GO
    ```

2.  <span data-ttu-id="c39c4-194">Настройте учетные данные [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] для входа администратора [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] . С их помощью хранилище ключей будет использоваться для настройки сценариев шифрования [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] и управления ими.</span><span class="sxs-lookup"><span data-stu-id="c39c4-194">Setup a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] credential for a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] administrator login to use the key vault in order to setup and manage [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] encryption scenarios.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="c39c4-195">Аргумент **Identity** для `CREATE CREDENTIAL` требует указания имени хранилища ключей.</span><span class="sxs-lookup"><span data-stu-id="c39c4-195">The **IDENTITY** argument of `CREATE CREDENTIAL` requires the key vault name.</span></span> <span data-ttu-id="c39c4-196">Для аргумента **Secret** параметра `CREATE CREDENTIAL` требуется *\<Client ID>* (без дефисов) и *\<Secret>* передаваться вместе без пробела между ними.</span><span class="sxs-lookup"><span data-stu-id="c39c4-196">The **SECRET** argument of `CREATE CREDENTIAL` requires the *\<Client ID>* (without hyphens) and *\<Secret>* to be passed together without a space between them.</span></span>

     <span data-ttu-id="c39c4-197">В следующем примере **идентификатор клиента** ( `EF5C8E09-4D2A-4A76-9998-D93440D8115D` ) удаляется из дефисов и указывается в виде строки `EF5C8E094D2A4A769998D93440D8115D` , а **секрет** представляется строкой *SECRET_sysadmin_login*.</span><span class="sxs-lookup"><span data-stu-id="c39c4-197">In the following example, the **Client ID** (`EF5C8E09-4D2A-4A76-9998-D93440D8115D`) is stripped of the hyphens and entered as the string `EF5C8E094D2A4A769998D93440D8115D` and the **Secret** is represented by the string *SECRET_sysadmin_login*.</span></span>

    ```sql
    USE master;
    CREATE CREDENTIAL sysadmin_ekm_cred 
        WITH IDENTITY = 'ContosoKeyVault', 
        SECRET = 'EF5C8E094D2A4A769998D93440D8115DSECRET_sysadmin_login' 
    FOR CRYPTOGRAPHIC PROVIDER AzureKeyVault_EKM_Prov ;

    -- Add the credential to the SQL Server administrators domain login 
    ALTER LOGIN [<domain>/<login>]
    ADD CREDENTIAL sysadmin_ekm_cred;
    ```

     <span data-ttu-id="c39c4-198">Пример использования переменных для `CREATE CREDENTIAL` аргументов и программного удаления дефисов из идентификатора клиента см. в статье [Создание учетных данных &#40;TRANSACT-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c39c4-198">For an example of using variables for the `CREATE CREDENTIAL` arguments and programmatically removing the hyphens from the Client ID, see [CREATE CREDENTIAL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql).</span></span>

3.  <span data-ttu-id="c39c4-199">Если вы импортировали асимметричный ключ, как описано выше в шаге 1 раздела 3, откройте ключ, указав имя ключа в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="c39c4-199">If you imported an asymmetric key as described earlier in step 1, section 3, open the key by providing your key name in the following example.</span></span>

    ```sql
    CREATE ASYMMETRIC KEY CONTOSO_KEY 
    FROM PROVIDER [AzureKeyVault_EKM_Prov]
    WITH PROVIDER_KEY_NAME = 'ContosoMasterKey',
    CREATION_DISPOSITION = OPEN_EXISTING;
    ```

     <span data-ttu-id="c39c4-200">Хотя это и не рекомендуется для рабочей среды (поскольку ключ невозможно экспортировать), можно создать асимметричный ключ напрямую в хранилище с помощью [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c39c4-200">Though not recommended for production (because the key cannot be exported), it is possible to create an asymmetric key directly in the vault from [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c39c4-201">Если вы не импортировали ключ ранее, создайте асимметричный ключ в хранилище для тестирования с помощью следующего скрипта.</span><span class="sxs-lookup"><span data-stu-id="c39c4-201">If you did not import a key earlier, then create an asymmetric key in the key vault for testing by using the following script.</span></span> <span data-ttu-id="c39c4-202">Выполните скрипт, используя имя входа, предоставленное в учетных данных **sysadmin_ekm_cred** .</span><span class="sxs-lookup"><span data-stu-id="c39c4-202">Execute the script, using a login provisioned with the **sysadmin_ekm_cred** credential.</span></span>

    ```sql
    CREATE ASYMMETRIC KEY CONTOSO_KEY 
    FROM PROVIDER [AzureKeyVault_EKM_Prov]
    WITH ALGORITHM = RSA_2048,
    PROVIDER_KEY_NAME = 'ContosoMasterKey';
    ```

> [!TIP]
>  <span data-ttu-id="c39c4-203">Пользователям, получившим сообщение об ошибке **Не удалось экспортировать открытый ключ от поставщика. Код ошибки поставщика: 2053.**</span><span class="sxs-lookup"><span data-stu-id="c39c4-203">Users receiving the error **Cannot export public key from the provider. Provider error code: 2053.**</span></span> <span data-ttu-id="c39c4-204">следует проверить в хранилище ключей свои разрешения **get**, **list**, **wrapKey**и **unwrapKey** в хранилище ключей.</span><span class="sxs-lookup"><span data-stu-id="c39c4-204">should check their **get**, **list**, **wrapKey**, and **unwrapKey** permissions in the key vault.</span></span>

 <span data-ttu-id="c39c4-205">Дополнительные сведения см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="c39c4-205">For more information, see the following:</span></span>

-   [<span data-ttu-id="c39c4-206">sp_configure (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="c39c4-206">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)

-   [<span data-ttu-id="c39c4-207">CREATE CRYPTOGRAPHIC PROVIDER &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c39c4-207">CREATE CRYPTOGRAPHIC PROVIDER &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-cryptographic-provider-transact-sql)

-   [<span data-ttu-id="c39c4-208">CREATE CREDENTIAL &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c39c4-208">CREATE CREDENTIAL &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-credential-transact-sql)

-   [<span data-ttu-id="c39c4-209">CREATE ASYMMETRIC KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c39c4-209">CREATE ASYMMETRIC KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-asymmetric-key-transact-sql)

-   [<span data-ttu-id="c39c4-210">CREATE LOGIN &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c39c4-210">CREATE LOGIN &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-login-transact-sql)

-   [<span data-ttu-id="c39c4-211">ALTER LOGIN &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c39c4-211">ALTER LOGIN &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-login-transact-sql)

## <a name="examples"></a><span data-ttu-id="c39c4-212">Примеры</span><span class="sxs-lookup"><span data-stu-id="c39c4-212">Examples</span></span>

###  <a name="example-a-transparent-data-encryption-by-using-an-asymmetric-key-from-the-key-vault"></a><a name="ExampleA"></a><span data-ttu-id="c39c4-213">Пример а. прозрачное шифрование данных с помощью асимметричного ключа из Key Vault</span><span class="sxs-lookup"><span data-stu-id="c39c4-213">Example A: Transparent Data Encryption by Using an Asymmetric Key from the Key Vault</span></span>
 <span data-ttu-id="c39c4-214">После выполнения действий, описанных выше, создайте учетные данные и имя входа, создайте ключ шифрования базы данных, защищенный асимметричным ключом, в хранилище ключей.</span><span class="sxs-lookup"><span data-stu-id="c39c4-214">After completing the steps above, create a credential and a login, create a database encryption key protected by the asymmetric key in the key vault.</span></span> <span data-ttu-id="c39c4-215">Используйте ключ для шифрования базы данных с помощью TDE.</span><span class="sxs-lookup"><span data-stu-id="c39c4-215">Use the database encryption key to encrypt a database with TDE.</span></span>

 <span data-ttu-id="c39c4-216">Для шифрования базы данных требуется разрешение CONTROL в базе данных.</span><span class="sxs-lookup"><span data-stu-id="c39c4-216">To encrypt a database requires CONTROL permission on the database.</span></span>

##### <a name="to-enable-tde-using-ekm-and-the-key-vault"></a><span data-ttu-id="c39c4-217">Включение прозрачного шифрования данных с помощью службы расширенного управления ключами и хранилища ключей</span><span class="sxs-lookup"><span data-stu-id="c39c4-217">To enable TDE using EKM and the Key Vault</span></span>

1.  <span data-ttu-id="c39c4-218">Создайте учетные данные [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] для [!INCLUDE[ssDE](../../../includes/ssde-md.md)] , которые будут использоваться при доступе к EKM хранилища ключей во время загрузки базы данных.</span><span class="sxs-lookup"><span data-stu-id="c39c4-218">Create a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] credential for the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] to use when accessing the key vault EKM during database load.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="c39c4-219">Аргумент **Identity** для `CREATE CREDENTIAL` требует указания имени хранилища ключей.</span><span class="sxs-lookup"><span data-stu-id="c39c4-219">The **IDENTITY** argument of `CREATE CREDENTIAL` requires the key vault name.</span></span> <span data-ttu-id="c39c4-220">Для аргумента **Secret** параметра `CREATE CREDENTIAL` требуется *\<Client ID>* (без дефисов) и *\<Secret>* передаваться вместе без пробела между ними.</span><span class="sxs-lookup"><span data-stu-id="c39c4-220">The **SECRET** argument of `CREATE CREDENTIAL` requires the *\<Client ID>* (without hyphens) and *\<Secret>* to be passed together without a space between them.</span></span>

     <span data-ttu-id="c39c4-221">В следующем примере из **идентификатора клиента** (`EF5C8E09-4D2A-4A76-9998-D93440D8115D`) удаляются дефисы. Идентификатор клиента вводится как строка `EF5C8E094D2A4A769998D93440D8115D` , а **секрет** представляется строкой *SECRET_DBEngine*.</span><span class="sxs-lookup"><span data-stu-id="c39c4-221">In the following example, the **Client ID** (`EF5C8E09-4D2A-4A76-9998-D93440D8115D`) is stripped of the hyphens and entered as the string `EF5C8E094D2A4A769998D93440D8115D` and the **Secret** is represented by the string *SECRET_DBEngine*.</span></span>

    ```sql
    USE master;
    CREATE CREDENTIAL Azure_EKM_TDE_cred 
        WITH IDENTITY = 'ContosoKeyVault', 
        SECRET = 'EF5C8E094D2A4A769998D93440D8115DSECRET_DBEngine' 
        FOR CRYPTOGRAPHIC PROVIDER AzureKeyVault_EKM_Prov ;
    ```

2.  <span data-ttu-id="c39c4-222">Создайте имя входа [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , которое будет использоваться [!INCLUDE[ssDE](../../../includes/ssde-md.md)] для прозрачного шифрования данных, и добавьте к нему учетные данные.</span><span class="sxs-lookup"><span data-stu-id="c39c4-222">Create a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] login to be used by the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] for TDE, and add the credential to it.</span></span> <span data-ttu-id="c39c4-223">В этом примере используется асимметричный ключ CONTOSO_KEY из хранилища ключей, который был импортирован или создан ранее для базы данных master, как описано в [шаге 3 раздела 3](#Step3) выше.</span><span class="sxs-lookup"><span data-stu-id="c39c4-223">This example uses the CONTOSO_KEY asymmetric key stored in the key vault, which was imported or created earlier for the master database, as described in [Step 3, section 3](#Step3) above.</span></span>

    ```sql
    USE master;
    -- Create a SQL Server login associated with the asymmetric key 
    -- for the Database engine to use when it loads a database 
    -- encrypted by TDE.
    CREATE LOGIN TDE_Login 
    FROM ASYMMETRIC KEY CONTOSO_KEY;
    GO 

    -- Alter the TDE Login to add the credential for use by the 
    -- Database Engine to access the key vault
    ALTER LOGIN TDE_Login 
    ADD CREDENTIAL Azure_EKM_TDE_cred ;
    GO
    ```

3.  <span data-ttu-id="c39c4-224">Создайте ключ шифрования базы данных (DEK), который будет использоваться для прозрачного шифрования данных.</span><span class="sxs-lookup"><span data-stu-id="c39c4-224">Create the database encryption key (DEK) that will be used for TDE.</span></span> <span data-ttu-id="c39c4-225">Ключ DEK можно создать, используя любой поддерживаемый алгоритм SQL Server или длину ключа.</span><span class="sxs-lookup"><span data-stu-id="c39c4-225">The DEK can be created using any SQL Server supported algorithm or key length.</span></span> <span data-ttu-id="c39c4-226">Ключ DEK будет защищен асимметричным ключом в хранилище ключей.</span><span class="sxs-lookup"><span data-stu-id="c39c4-226">The DEK will be protected by the asymmetric key in the key vault.</span></span>

     <span data-ttu-id="c39c4-227">В этом примере используется асимметричный ключ CONTOSO_KEY из хранилища ключей, который был импортирован или создан ранее, как описано в [шаге 3 раздела 3](#Step3) выше.</span><span class="sxs-lookup"><span data-stu-id="c39c4-227">This example uses the CONTOSO_KEY asymmetric key stored in the key vault, which was imported or created earlier, as described in [Step 3, section 3](#Step3) above.</span></span>

    ```sql
    USE ContosoDatabase;
    GO

    CREATE DATABASE ENCRYPTION KEY 
    WITH ALGORITHM = AES_128 
    ENCRYPTION BY SERVER ASYMMETRIC KEY CONTOSO_KEY;
    GO

    -- Alter the database to enable transparent data encryption.
    ALTER DATABASE ContosoDatabase 
    SET ENCRYPTION ON ;
    GO
    ```

     <span data-ttu-id="c39c4-228">Дополнительные сведения см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="c39c4-228">For more information, see the following:</span></span>

    -   [<span data-ttu-id="c39c4-229">CREATE DATABASE ENCRYPTION KEY (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="c39c4-229">CREATE DATABASE ENCRYPTION KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-database-encryption-key-transact-sql)

    -   [<span data-ttu-id="c39c4-230">ALTER DATABASE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="c39c4-230">ALTER DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql)

###  <a name="example-b-encrypting-backups-by-using-an-asymmetric-key-from-the-key-vault"></a><a name="ExampleB"></a><span data-ttu-id="c39c4-231">Пример б. шифрование резервных копий с помощью асимметричного ключа из Key Vault</span><span class="sxs-lookup"><span data-stu-id="c39c4-231">Example B: Encrypting Backups by Using an Asymmetric Key from the Key Vault</span></span>
 <span data-ttu-id="c39c4-232">Зашифрованные резервные копии поддерживаются начиная с [!INCLUDE[ssSQL14](../../../includes/sssql14-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c39c4-232">Encrypted backups are supported starting with [!INCLUDE[ssSQL14](../../../includes/sssql14-md.md)].</span></span> <span data-ttu-id="c39c4-233">В следующем примере создается и восстанавливается резервная копия, зашифрованная ключом шифрования данных, который защищен асимметричным ключом в хранилище ключей.</span><span class="sxs-lookup"><span data-stu-id="c39c4-233">The following example creates and restores a backup encrypted a data encryption key protected by the asymmetric key in the key vault.</span></span>

```sql
USE master;
BACKUP DATABASE [DATABASE_TO_BACKUP]
TO DISK = N'[PATH TO BACKUP FILE]' 
WITH FORMAT, INIT, SKIP, NOREWIND, NOUNLOAD, 
ENCRYPTION(ALGORITHM = AES_256, SERVER ASYMMETRIC KEY = [CONTOSO_KEY]);
GO
```

 <span data-ttu-id="c39c4-234">Образец кода восстановления.</span><span class="sxs-lookup"><span data-stu-id="c39c4-234">Sample restore code.</span></span>

```sql
RESTORE DATABASE [DATABASE_TO_BACKUP]
FROM DISK = N'[PATH TO BACKUP FILE]' WITH FILE = 1, NOUNLOAD, REPLACE;
GO
```

 <span data-ttu-id="c39c4-235">Дополнительные сведения о параметрах резервного копирования см. в разделе [backup &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c39c4-235">For more information about backup options, see [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span></span>

###  <a name="example-c-column-level-encryption-by-using-an-asymmetric-key-from-the-key-vault"></a><a name="ExampleC"></a><span data-ttu-id="c39c4-236">Пример в. шифрование на уровне столбцов с помощью асимметричного ключа из Key Vault</span><span class="sxs-lookup"><span data-stu-id="c39c4-236">Example C: Column Level Encryption by Using an Asymmetric Key from the Key Vault</span></span>
 <span data-ttu-id="c39c4-237">В следующем примере создается симметричный ключ, защищенный асимметричным ключом в хранилище ключей.</span><span class="sxs-lookup"><span data-stu-id="c39c4-237">The following example creates a symmetric key protected by the asymmetric key in the key vault.</span></span> <span data-ttu-id="c39c4-238">Затем симметричный ключ используется для шифрования данных в базе данных.</span><span class="sxs-lookup"><span data-stu-id="c39c4-238">Then the symmetric key is used to encrypt data in the database.</span></span>

 <span data-ttu-id="c39c4-239">В этом примере используется асимметричный ключ CONTOSO_KEY из хранилища ключей, который был импортирован или создан ранее, как описано в [шаге 3 раздела 3](#Step3) выше.</span><span class="sxs-lookup"><span data-stu-id="c39c4-239">This example uses the CONTOSO_KEY asymmetric key stored in the key vault, which was imported or created earlier, as described in [Step 3, section 3](#Step3) above.</span></span> <span data-ttu-id="c39c4-240">Чтобы использовать асимметричный ключ в базе данных `ContosoDatabase` , необходимо выполнить инструкцию CREATE ASYMMETRIC KEY еще раз, чтобы предоставить базе данных `ContosoDatabase` ссылку на ключ.</span><span class="sxs-lookup"><span data-stu-id="c39c4-240">To use this asymmetric key in the `ContosoDatabase` database, you must execute the CREATE ASYMMETRIC KEY statement again, to provide the `ContosoDatabase` database with a reference to the key.</span></span>

```sql
USE [ContosoDatabase];
GO

-- Create a reference to the key in the key vault
CREATE ASYMMETRIC KEY CONTOSO_KEY 
FROM PROVIDER [AzureKeyVault_EKM_Prov]
WITH PROVIDER_KEY_NAME = 'ContosoMasterKey',
CREATION_DISPOSITION = OPEN_EXISTING;

-- Create the data encryption key.
-- The data encryption key can be created using any SQL Server 
-- supported algorithm or key length.
-- The DEK will be protected by the asymmetric key in the key vault

CREATE SYMMETRIC KEY DATA_ENCRYPTION_KEY
    WITH ALGORITHM=AES_256
    ENCRYPTION BY ASYMMETRIC KEY CONTOSO_KEY;

DECLARE @DATA VARBINARY(MAX);

--Open the symmetric key for use in this session
OPEN SYMMETRIC KEY DATA_ENCRYPTION_KEY 
DECRYPTION BY ASYMMETRIC KEY CONTOSO_KEY;

--Encrypt syntax
SELECT @DATA = ENCRYPTBYKEY(KEY_GUID('DATA_ENCRYPTION_KEY'), CONVERT(VARBINARY,'Plain text data to encrypt'));

-- Decrypt syntax
SELECT CONVERT(VARCHAR, DECRYPTBYKEY(@DATA));

--Close the symmetric key
CLOSE SYMMETRIC KEY DATA_ENCRYPTION_KEY;
```

## <a name="see-also"></a><span data-ttu-id="c39c4-241">См. также:</span><span class="sxs-lookup"><span data-stu-id="c39c4-241">See Also</span></span>
 <span data-ttu-id="c39c4-242">[Создание поставщика служб шифрования &#40;Transact-sql&#41;](/sql/t-sql/statements/create-cryptographic-provider-transact-sql) [Создание учетных данных &#40;transact-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql) [CREATE асимметричный ключ &#40;TRANSACT-SQL&#41;](/sql/t-sql/statements/create-asymmetric-key-transact-sql) [Создание симметричного ключа &#40;Transact-](/sql/t-sql/statements/create-symmetric-key-transact-sql) SQL&#41;[Расширенное управление ключами &#40;расширенный](extensible-key-management-ekm.md) ключ&#41;[Включение TDE с помощью](enable-tde-on-sql-server-using-ekm.md) [шифрования резервных копий](../../backup-restore/backup-encryption.md) [Create an Encrypted Backup](../../backup-restore/create-an-encrypted-backup.md)</span><span class="sxs-lookup"><span data-stu-id="c39c4-242">[CREATE CRYPTOGRAPHIC PROVIDER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-cryptographic-provider-transact-sql) [CREATE CREDENTIAL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql) [CREATE ASYMMETRIC KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-asymmetric-key-transact-sql) [CREATE SYMMETRIC KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-symmetric-key-transact-sql) [Extensible Key Management &#40;EKM&#41;](extensible-key-management-ekm.md) [Enable TDE Using EKM](enable-tde-on-sql-server-using-ekm.md) [Backup Encryption](../../backup-restore/backup-encryption.md) [Create an Encrypted Backup](../../backup-restore/create-an-encrypted-backup.md)</span></span>
