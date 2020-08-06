---
title: Диспетчер подключений службы хранилища Azure | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.afpstorageconn.f1
- sql11.dts.designer.afpstorageconn.f1
ms.assetid: 68bd1d04-d20f-4357-a34e-7c9c76457062
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 47580d8d1d961df9fbcbed0bd7164f1c54792b86
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664447"
---
# <a name="azure-storage-connection-manager"></a><span data-ttu-id="389ad-102">Диспетчер подключений службы хранилища Azure</span><span class="sxs-lookup"><span data-stu-id="389ad-102">Azure Storage Connection Manager</span></span>
  <span data-ttu-id="389ad-103">Диспетчер подключений службы хранилища Azure позволяет использовать пакет SSIS для подключения к учетной записи хранения Azure с помощью указываемых значений свойств: имени учетной записи хранения и ключа учетной записи.</span><span class="sxs-lookup"><span data-stu-id="389ad-103">The Azure Storage connection manager enables an SSIS package to connect to an Azure Storage account by using the values you specify for the properties: Storage Account Name and Account Key.</span></span>  
  
1.  <span data-ttu-id="389ad-104">В диалоговом окне **Добавление диспетчера соединений со службами SSIS** выберите **AzureStorage**и щелкните **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="389ad-104">In the **Add SSIS Connection Manager** dialog box, select **AzureStorage**, and click **Add**.</span></span>  
  
2.  <span data-ttu-id="389ad-105">В диалоговом окне редактора диспетчера подключений службы хранилища Azure выберите **Use Azure account** (Использовать учетную запись Azure), чтобы подключиться к службе хранилища Azure через Интернет, или выберите **Use local developer account** (Использовать локальную учетную запись разработчика), чтобы подключиться к локальной службе, размещенной эмулятором хранения Azure.</span><span class="sxs-lookup"><span data-stu-id="389ad-105">In the Azure Storage Connection Manager Editor dialog box, choose **Use Azure account** to connect to an Azure Storage Service via internet or choose **Use local developer account** to connect to the local service hosted by the Azure Storage Emulator.</span></span>  
  
3.  <span data-ttu-id="389ad-106">Если вы выбрали параметр **Use Azure account** (Использовать учетную запись Azure), выполните следующее.</span><span class="sxs-lookup"><span data-stu-id="389ad-106">If you selected **Use Azure account** option, do the following:</span></span>  
  
    1.  <span data-ttu-id="389ad-107">Укажите значения для полей **Имя учетной записи хранения** и **Ключ учетной записи** .</span><span class="sxs-lookup"><span data-stu-id="389ad-107">Specify values for the **Storage account name** and **Account key** field.</span></span> <span data-ttu-id="389ad-108">Эти значения будут храниться как конфиденциальные данные в пакете SSIS.</span><span class="sxs-lookup"><span data-stu-id="389ad-108">These values will be stored as sensitive data in SSIS package.</span></span>  
  
    2.  <span data-ttu-id="389ad-109">Выберите параметр **Использовать HTTPS** , если для подключения к службе хранилища Azure хотите использовать протокол HTTPS, а не HTTP.</span><span class="sxs-lookup"><span data-stu-id="389ad-109">Select **Use HTTPS** if you want to use HTTPS instead of HTTP to connect to the Azure Storage Service.</span></span>  
  
4.  <span data-ttu-id="389ad-110">Чтобы закрыть диалоговое окно, нажмите кнопку **ОК** .</span><span class="sxs-lookup"><span data-stu-id="389ad-110">Click **OK** to close the dialog box.</span></span>  
  
5.  <span data-ttu-id="389ad-111">Свойства созданного диспетчера соединений можно просмотреть в окне **Свойства** .</span><span class="sxs-lookup"><span data-stu-id="389ad-111">You can see the properties of the connection manager you created in the **Properties** window.</span></span>  
  
  
