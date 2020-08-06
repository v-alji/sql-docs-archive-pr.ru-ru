---
title: Подключение к службе хранилища Azure (восстановление) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.restore.connectstorage.f1
ms.assetid: c0b7d7c8-b878-4b7f-8120-d0c6917b583f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: dff9730d6592381b1c8e8a1cf7ee45ad7532a440
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668932"
---
# <a name="connect-to-azure-storage-restore"></a><span data-ttu-id="e6062-102">Подключение к службе хранилища Azure (восстановление)</span><span class="sxs-lookup"><span data-stu-id="e6062-102">Connect to Azure Storage (Restore)</span></span>
  <span data-ttu-id="e6062-103">Это диалоговое окно позволяет указать сведения для подключения к учетной записи хранения Azure с целью получения хранилища файлов в учетной записи хранения.</span><span class="sxs-lookup"><span data-stu-id="e6062-103">The dialog box allows you to specify the connection to Azure storage account information in order to retrieve the files storage in the Azure storage account.</span></span> <span data-ttu-id="e6062-104">После ввода необходимой информации нажмите кнопку **Подключить**, чтобы подключиться к хранилищу Azure.</span><span class="sxs-lookup"><span data-stu-id="e6062-104">After specifying the required information, click **Connect** to establish the connection to Azure storage.</span></span>  
  
## <a name="azure-storage-account"></a><span data-ttu-id="e6062-105">Учетная запись хранения Azure</span><span class="sxs-lookup"><span data-stu-id="e6062-105">Azure Storage Account</span></span>  
 <span data-ttu-id="e6062-106">**Учетная запись хранения**</span><span class="sxs-lookup"><span data-stu-id="e6062-106">**Storage account**</span></span>  
 <span data-ttu-id="e6062-107">Выберите, введите или вставьте имя учетной записи хранения Azure.</span><span class="sxs-lookup"><span data-stu-id="e6062-107">Select, type or paste the name of the Azure storage account you want to use.</span></span> <span data-ttu-id="e6062-108">В раскрывающемся списке указаны ранее используемые учетные записи.</span><span class="sxs-lookup"><span data-stu-id="e6062-108">The drop down box lists the accounts previously used.</span></span>  
  
 <span data-ttu-id="e6062-109">**Ключ учетной записи**</span><span class="sxs-lookup"><span data-stu-id="e6062-109">**Account key**</span></span>  
 <span data-ttu-id="e6062-110">Укажите ключ доступа к учетной записи хранения Azure.</span><span class="sxs-lookup"><span data-stu-id="e6062-110">Specify the Azure storage account access key.</span></span>  
  
 <span data-ttu-id="e6062-111">Флажок**Использовать защищенные конечные точки (HTTPS)**</span><span class="sxs-lookup"><span data-stu-id="e6062-111">**Use secure endpoints (HTTPS)** check box</span></span>  
 <span data-ttu-id="e6062-112">Установите этот флажок, чтобы установить безопасное подключение с хранилищу Azure (рекомендуется).</span><span class="sxs-lookup"><span data-stu-id="e6062-112">Select this option to make a secure connection to Azure storage - recommended.</span></span>  
  
 <span data-ttu-id="e6062-113">Флажок**Сохранить мой ключ учетной записи**</span><span class="sxs-lookup"><span data-stu-id="e6062-113">**Save account key** check box</span></span>  
 <span data-ttu-id="e6062-114">Установите этот флажок, чтобы SQL Server запоминал ключ доступа для этой учетной записи хранения.</span><span class="sxs-lookup"><span data-stu-id="e6062-114">Select this check box if you want SQL Server to remember the access key for this storage account.</span></span>  
  
### <a name="sql-credential"></a><span data-ttu-id="e6062-115">Учетные данные SQL</span><span class="sxs-lookup"><span data-stu-id="e6062-115">SQL Credential</span></span>  
 <span data-ttu-id="e6062-116">**Выбор существующих учетных данных**</span><span class="sxs-lookup"><span data-stu-id="e6062-116">**Select an existing credential**</span></span>  
 <span data-ttu-id="e6062-117">Выберите существующие учетные данные SQL, соответствующие учетной записи хранения и ключу доступа.</span><span class="sxs-lookup"><span data-stu-id="e6062-117">Select an existing SQL Credential that matches the storage account and account key information.</span></span>  
  
 <span data-ttu-id="e6062-118">**Создание новых учетных данных**</span><span class="sxs-lookup"><span data-stu-id="e6062-118">**Create a new Credential**</span></span>  
 <span data-ttu-id="e6062-119">Выберите этот параметр, чтобы создать новые учетные данные, используя учетную запись хранения и ключ доступа.</span><span class="sxs-lookup"><span data-stu-id="e6062-119">Select this option to create a new credential using the storage account and account key information.</span></span> <span data-ttu-id="e6062-120">Введите имя учетных данных в поле **Имя учетных данных** .</span><span class="sxs-lookup"><span data-stu-id="e6062-120">Specify the name of the new credential in the **Credential Name** field.</span></span>  
  
  
