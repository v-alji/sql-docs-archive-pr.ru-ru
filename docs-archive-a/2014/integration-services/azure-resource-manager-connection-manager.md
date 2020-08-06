---
title: Диспетчер подключений Azure Resource Manager | Документы Майкрософт
ms.custom: ''
ms.date: 02/28/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- SQL12.DTS.DESIGNER.AFPARMCM.F1
- SQL11.DTS.DESIGNER.AFPARMCM.F1
ms.assetid: a2380258-0418-4a8c-a731-5071a44ddf1e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1dce4def11f14072295dbf3cde9d5ab77304fe74
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665095"
---
# <a name="azure-resource-manager-connection-manager"></a><span data-ttu-id="2a879-102">Диспетчер подключений Azure Resource Manager</span><span class="sxs-lookup"><span data-stu-id="2a879-102">Azure Resource Manager Connection Manager</span></span>
<span data-ttu-id="2a879-103">**Диспетчер подключений Azure Resource Manager** позволяет пакету служб SSIS управлять ресурсами Azure с помощью [субъекта-службы](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-create-service-principal-portal).</span><span class="sxs-lookup"><span data-stu-id="2a879-103">The **Azure Resource Manager Connection Manager** enables an SSIS package to manage Azure resources using a [service principal](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-create-service-principal-portal).</span></span>

<span data-ttu-id="2a879-104">Чтобы создать и настроить **диспетчер подключений Azure Resource Manager**, выполните указанные ниже действия:</span><span class="sxs-lookup"><span data-stu-id="2a879-104">To create and configure an **Azure Resource Manager Connection Manager**, follow the steps below:</span></span>

1. <span data-ttu-id="2a879-105">В диалоговом окне **Добавление диспетчера соединений со службами SSIS** выберите **AzureResourceManager**и щелкните **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="2a879-105">In the **Add SSIS Connection Manager** dialog box, select **AzureResourceManager**, and click **Add**.</span></span>
2. <span data-ttu-id="2a879-106">В диалоговом окне **редактора диспетчера подключений Azure Resource Manager** укажите **Идентификатор приложения**, **Ключ приложения** и **Идентификатор клиента** для субъекта-службы.</span><span class="sxs-lookup"><span data-stu-id="2a879-106">In the **Azure Resource Manager Connection Manager Editor** dialog box, specify the **Application ID**, **Application Key**, and **Tenant ID** for the service principal.</span></span> <span data-ttu-id="2a879-107">Дополнительные сведения об этих свойствах см. [этой](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-create-service-principal-portal) статье.</span><span class="sxs-lookup"><span data-stu-id="2a879-107">For details about these properties, please refer to [this](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-create-service-principal-portal) article.</span></span>
3. <span data-ttu-id="2a879-108">Чтобы закрыть диалоговое окно, нажмите кнопку **ОК** .</span><span class="sxs-lookup"><span data-stu-id="2a879-108">Click **OK** to close the dialog box.</span></span>
4. <span data-ttu-id="2a879-109">Свойства созданного диспетчера соединений можно просмотреть в окне **Свойства** .</span><span class="sxs-lookup"><span data-stu-id="2a879-109">You can see the properties of the connection manager you created in the **Properties** window.</span></span>
