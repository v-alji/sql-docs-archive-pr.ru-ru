---
title: Основные сведения о поставщике WMI для управления конфигурацией | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
helpviewer_keywords:
- WMI Provider for Configuration Management, operations supported
ms.assetid: 92323972-7943-4208-bbf4-050774fb6027
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 0f4f38265093fdb0c27d6bd49ff64ba4b572111e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654074"
---
# <a name="understanding-the-wmi-provider-for-configuration-management"></a><span data-ttu-id="639b6-102">Основные сведения о поставщике WMI для управления конфигурацией</span><span class="sxs-lookup"><span data-stu-id="639b6-102">Understanding the WMI Provider for Configuration Management</span></span>
  [!INCLUDE[msCoName](../../includes/msconame-md.md)]<span data-ttu-id="639b6-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]предоставляет поставщик WMI для управления конфигурацией.</span><span class="sxs-lookup"><span data-stu-id="639b6-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provides the WMI Provider for Configuration Management.</span></span> <span data-ttu-id="639b6-104">Это позволяет использовать инструментарий управления Windows для управления службами [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], клиентом [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], сетевыми параметрами сервера и его псевдонимами.</span><span class="sxs-lookup"><span data-stu-id="639b6-104">This lets you use Windows Management Instrumentation (WMI) to manage [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client and server network settings, and server aliases.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="639b6-105">службы, сетевые параметры и псевдонимы представлены объектами WMI в пространстве имен Рут\микрософт\склсервер\компутерманажемент*nn* компьютера.</span><span class="sxs-lookup"><span data-stu-id="639b6-105">services, network settings, and aliases are represented by WMI objects in the root\Microsoft\SqlServer\ComputerManagement*nn* namespace of the computer.</span></span> <span data-ttu-id="639b6-106">После установления соединения с поставщиком WMI на некотором компьютере службы сетевые параметры и псевдонимы можно запрашивать с помощью WQL или языка сценариев.</span><span class="sxs-lookup"><span data-stu-id="639b6-106">After a connection is established with the WMI provider on the specified computer, the services, network settings, and aliases can be queried using WQL or a scripting language.</span></span>  
  
 <span data-ttu-id="639b6-107">Поставщик WMI является поставщиком экземпляров.</span><span class="sxs-lookup"><span data-stu-id="639b6-107">The WMI Provider is an instance provider.</span></span> <span data-ttu-id="639b6-108">Он предоставляет экземпляры [классов WMI](../wmi-provider-configuration-classes/wmi-provider-for-configuration-management-classes.md) и поддерживает следующие асинхронные операции.</span><span class="sxs-lookup"><span data-stu-id="639b6-108">It supplies instances of the [WMI Classes](../wmi-provider-configuration-classes/wmi-provider-for-configuration-management-classes.md) and supports the following asynchronous operations.</span></span>  
  
 <span data-ttu-id="639b6-109">Получение экземпляра</span><span class="sxs-lookup"><span data-stu-id="639b6-109">Instance retrieval</span></span>  
 <span data-ttu-id="639b6-110">Получение экземпляра определенного типа класса.</span><span class="sxs-lookup"><span data-stu-id="639b6-110">Retrieval of a particular class type instance.</span></span>  
  
 <span data-ttu-id="639b6-111">Перечисление</span><span class="sxs-lookup"><span data-stu-id="639b6-111">Enumeration</span></span>  
 <span data-ttu-id="639b6-112">Перечисление всех экземпляров типа класса.</span><span class="sxs-lookup"><span data-stu-id="639b6-112">Enumeration of all instances of a class type.</span></span>  
  
 <span data-ttu-id="639b6-113">Изменение</span><span class="sxs-lookup"><span data-stu-id="639b6-113">Modification</span></span>  
 <span data-ttu-id="639b6-114">Изменение определенного экземпляра типа класса.</span><span class="sxs-lookup"><span data-stu-id="639b6-114">Modification of a particular instance of a class type.</span></span>  
  
 <span data-ttu-id="639b6-115">Классы содержат методы, позволяющие изменять их свойства.</span><span class="sxs-lookup"><span data-stu-id="639b6-115">Classes have methods that allow the modification of their properties.</span></span>  
  
 <span data-ttu-id="639b6-116">Удаление</span><span class="sxs-lookup"><span data-stu-id="639b6-116">Deletion</span></span>  
 <span data-ttu-id="639b6-117">Удаление определенного экземпляра типа класса.</span><span class="sxs-lookup"><span data-stu-id="639b6-117">Removing a particular instance of a class type.</span></span>  
  
 <span data-ttu-id="639b6-118">Обработка запросов</span><span class="sxs-lookup"><span data-stu-id="639b6-118">Query processing</span></span>  
 <span data-ttu-id="639b6-119">Перечисление экземпляров типа класса на основе фильтра.</span><span class="sxs-lookup"><span data-stu-id="639b6-119">Enumeration of instances of a class type based on a filter.</span></span>  
  
 <span data-ttu-id="639b6-120">Примеры приложения управления с помощью поставщика WMI для управления конфигурацией см. в разделе [Использование WQL и языков сценариев с поставщиком WMI для управления конфигурацией](using-wql-and-scripting-languages-with-the-wmi-provider.md).</span><span class="sxs-lookup"><span data-stu-id="639b6-120">For examples of management application using the WMI Provider for Configuration Management, see [Using WQL and Scripting Languages with the WMI Provider for Configuration Management](using-wql-and-scripting-languages-with-the-wmi-provider.md).</span></span>  
  
 <span data-ttu-id="639b6-121">Дополнительные сведения о приложениях для управления программированием с помощью поставщика WMI см. в документации по инструментарию WMI в [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework SDK.</span><span class="sxs-lookup"><span data-stu-id="639b6-121">For more information about programming management applications using the WMI Provider, see the WMI documentation in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework SDK.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="639b6-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="639b6-122">See Also</span></span>  
 <span data-ttu-id="639b6-123">[Работа с поставщиком WMI для управления конфигурацией](working-with-the-wmi-provider-for-configuration-management.md) </span><span class="sxs-lookup"><span data-stu-id="639b6-123">[Working with the WMI Provider for Configuration Management](working-with-the-wmi-provider-for-configuration-management.md) </span></span>  
 [<span data-ttu-id="639b6-124">Использование WQL и языков сценариев с поставщиком WMI для управления конфигурациями</span><span class="sxs-lookup"><span data-stu-id="639b6-124">Using WQL and Scripting Languages with the WMI Provider for Configuration Management</span></span>](using-wql-and-scripting-languages-with-the-wmi-provider.md)  
  
  
