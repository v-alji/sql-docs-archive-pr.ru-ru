---
title: Создание учетных данных — аутентификация в хранилище Azure | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.backuptourl.createcred.f1
ms.assetid: 0622619d-27c5-4ff0-83e5-cde31648c27a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: afdbf2647c79e07cf3f190ec6710eeb6b7718f6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87740073"
---
# <a name="create-credential---authenticate-to-azure-storage"></a><span data-ttu-id="9587a-102">Создание учетных данных — проверка подлинности в хранилище Azure</span><span class="sxs-lookup"><span data-stu-id="9587a-102">Create Credential - Authenticate to Azure Storage</span></span>
  <span data-ttu-id="9587a-103">Чтобы создать учетные данные SQL, воспользуйтесь диалоговым окном **Резервное копирование по URL-адресу — создать учетные данные**.</span><span class="sxs-lookup"><span data-stu-id="9587a-103">Use the **Backup to URL - Create Credential** dialog box to create a new SQL Credential.</span></span>  
  
 <span data-ttu-id="9587a-104">При создании учетных данных с помощью этого диалогового окна необходимо предоставить сертификат управления Azure, добавленный в локальное хранилище сертификатов, или профиль публикации, скачанный на компьютер для проверки подписки и сведений об учетной записи хранения.</span><span class="sxs-lookup"><span data-stu-id="9587a-104">When using this dialog box to create a credential, you must provide an Azure Management Certificate added to the local certificate store or a publishing profile downloaded to your computer to validate the subscription and the storage account information.</span></span>  
  
 <span data-ttu-id="9587a-105">**Учетные данные SQL**</span><span class="sxs-lookup"><span data-stu-id="9587a-105">**SQL Credential**</span></span>  
 <span data-ttu-id="9587a-106">Задайте имя создаваемых учетных данных SQL.</span><span class="sxs-lookup"><span data-stu-id="9587a-106">Specify the name of the SQL Credential you want to create.</span></span>  
  
## <a name="azure-credentials"></a><span data-ttu-id="9587a-107">Учетные данные Azure</span><span class="sxs-lookup"><span data-stu-id="9587a-107">Azure Credentials</span></span>  
 <span data-ttu-id="9587a-108">**Сертификат управления**</span><span class="sxs-lookup"><span data-stu-id="9587a-108">**Management Certificate**</span></span>  
 <span data-ttu-id="9587a-109">Используйте этот параметр, чтобы указать сертификат из локального хранилища сертификатов, соответствующий сертификату управления из Azure.</span><span class="sxs-lookup"><span data-stu-id="9587a-109">Use this option to specify a certificate from the local certificate store that matches the management certificate from Azure.</span></span> <span data-ttu-id="9587a-110">Дополнительные сведения о сертификате управления Azure см. в статье [Create and Upload a Management Certificate for Azure](https://go.microsoft.com/fwlink/?LinkId=320781) (Создание и передача сертификата управления для Azure).</span><span class="sxs-lookup"><span data-stu-id="9587a-110">For more information on Azure management certificate, see [Create and Upload a Management Certificate for Azure](https://go.microsoft.com/fwlink/?LinkId=320781).</span></span>  
  
 <span data-ttu-id="9587a-111">**Подписка**</span><span class="sxs-lookup"><span data-stu-id="9587a-111">**Subscription**</span></span>  
 <span data-ttu-id="9587a-112">Выберите, введите или вставьте идентификатор подписки Azure, который соответствует сертификату управления из локального хранилища сертификатов.</span><span class="sxs-lookup"><span data-stu-id="9587a-112">Select, type, or paste your Azure subscription ID that matches the management certificate from the local certificate store.</span></span>  
  
 <span data-ttu-id="9587a-113">**Профиль публикации**</span><span class="sxs-lookup"><span data-stu-id="9587a-113">**Publishing Profile**</span></span>  
 <span data-ttu-id="9587a-114">Используйте этот параметр, если имеется профиль публикации, загруженный на компьютер.</span><span class="sxs-lookup"><span data-stu-id="9587a-114">Use this option if you have a publishing profile downloaded to your computer.</span></span> <span data-ttu-id="9587a-115">Если воспользоваться этим параметром, идентификатор подписки и сертификат будут заполнены автоматически.</span><span class="sxs-lookup"><span data-stu-id="9587a-115">If you use this option, the subscription ID, and the certificate are auto populated.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="9587a-116">SQL Server в настоящий момент поддерживает версию 2.0 профиля публикации.</span><span class="sxs-lookup"><span data-stu-id="9587a-116">SQL Server currently supports publishing profile version 2.0.</span></span> <span data-ttu-id="9587a-117">Для загрузки поддерживаемой версии профиля публикации см. раздел [Загрузка профиля публикации 2.0](https://go.microsoft.com/fwlink/?LinkId=396421).</span><span class="sxs-lookup"><span data-stu-id="9587a-117">To download the supported version of the publishing profile, see [Download Publishing Profile 2.0](https://go.microsoft.com/fwlink/?LinkId=396421).</span></span>  
  
## <a name="storage-account"></a><span data-ttu-id="9587a-118">Учетная запись хранения</span><span class="sxs-lookup"><span data-stu-id="9587a-118">Storage Account</span></span>  
 <span data-ttu-id="9587a-119">Выберите учетную запись хранения, которую нужно использовать для хранения файлов резервных копий.</span><span class="sxs-lookup"><span data-stu-id="9587a-119">Select the storage account you want to use to store the backup files on.</span></span>  
  
  
