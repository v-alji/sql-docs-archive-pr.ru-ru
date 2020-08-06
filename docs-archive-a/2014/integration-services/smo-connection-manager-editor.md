---
title: Редактор диспетчера соединений SMO | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.smoconnection.f1
helpviewer_keywords:
- SMO Connection Manager Editor
ms.assetid: bed52d80-ed2a-4bf4-bf7c-481b6e228ca4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6b3d1ccea1a3a4e963c6b6f8c7dbd58a374b3de4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751252"
---
# <a name="smo-connection-manager-editor"></a><span data-ttu-id="83fcb-102">редактор диспетчера соединений SMO</span><span class="sxs-lookup"><span data-stu-id="83fcb-102">SMO Connection Manager Editor</span></span>
  <span data-ttu-id="83fcb-103">Используйте **Редактор диспетчера соединений SMO** для настройки соединения сервера [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , которое может использоваться различными задачами, переносящими объекты [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="83fcb-103">Use the **SMO Connection Manager Editor** to configure a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] connection for use by the various tasks that transfer [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] objects.</span></span>  
  
 <span data-ttu-id="83fcb-104">Дополнительные сведения о диспетчере соединений объектов SMO см. в разделе [SMO Connection Manager](connection-manager/smo-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="83fcb-104">To learn more about the SMO connection manager, see [SMO Connection Manager](connection-manager/smo-connection-manager.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="83fcb-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="83fcb-105">Options</span></span>  
 <span data-ttu-id="83fcb-106">**Имя сервера**</span><span class="sxs-lookup"><span data-stu-id="83fcb-106">**Server name**</span></span>  
 <span data-ttu-id="83fcb-107">Введите имя экземпляра сервера [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] или выберите имя сервера из списка.</span><span class="sxs-lookup"><span data-stu-id="83fcb-107">Type the name of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance or select the server name from the list.</span></span>  
  
 <span data-ttu-id="83fcb-108">**Обновить**</span><span class="sxs-lookup"><span data-stu-id="83fcb-108">**Refresh**</span></span>  
 <span data-ttu-id="83fcb-109">Обновите список доступных экземпляров сервера [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , которые могут быть обнаружены в сети.</span><span class="sxs-lookup"><span data-stu-id="83fcb-109">Refresh the list of available [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instances that can be detected on the network.</span></span>  
  
 <span data-ttu-id="83fcb-110">**Использовать проверку подлинности Windows**</span><span class="sxs-lookup"><span data-stu-id="83fcb-110">**Use Windows Authentication**</span></span>  
 <span data-ttu-id="83fcb-111">Используйте проверку подлинности Windows для подключения к выбранному экземпляру сервера [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="83fcb-111">Use Windows Authentication to connect to the selected [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance.</span></span>  
  
 <span data-ttu-id="83fcb-112">**Использовать проверку подлинности SQL Server**</span><span class="sxs-lookup"><span data-stu-id="83fcb-112">**Use SQL Server Authentication**</span></span>  
 <span data-ttu-id="83fcb-113">Используйте проверку подлинности сервера [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] для подключения к выбранному экземпляру сервера [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="83fcb-113">Use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication to connect to the selected [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance.</span></span>  
  
 <span data-ttu-id="83fcb-114">**User name**</span><span class="sxs-lookup"><span data-stu-id="83fcb-114">**User name**</span></span>  
 <span data-ttu-id="83fcb-115">При выборе проверки подлинности сервера [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] введите имя пользователя сервера [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="83fcb-115">If you have selected [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] authentication, enter the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] user name.</span></span>  
  
 <span data-ttu-id="83fcb-116">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="83fcb-116">**Password**</span></span>  
 <span data-ttu-id="83fcb-117">При выборе проверки подлинности сервера [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] введите пароль.</span><span class="sxs-lookup"><span data-stu-id="83fcb-117">If you have selected [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] authentication, enter the password.</span></span>  
  
 <span data-ttu-id="83fcb-118">**Проверка соединения**</span><span class="sxs-lookup"><span data-stu-id="83fcb-118">**Test Connection**</span></span>  
 <span data-ttu-id="83fcb-119">Проверка соединения согласно настройке.</span><span class="sxs-lookup"><span data-stu-id="83fcb-119">Test the connection as configured.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83fcb-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="83fcb-120">See Also</span></span>  
 [<span data-ttu-id="83fcb-121">Справочник по сообщениям об ошибках служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="83fcb-121">Integration Services Error and Message Reference</span></span>](../../2014/integration-services/integration-services-error-and-message-reference.md)  
  
  
