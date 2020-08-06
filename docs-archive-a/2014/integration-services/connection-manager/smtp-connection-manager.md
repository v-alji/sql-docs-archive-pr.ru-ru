---
title: Диспетчер подключений SMTP | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- connections [Integration Services], SMTP
- SMTP connection manager [Integration Services]
- connection managers [Integration Services], SMTP
ms.assetid: 3795d442-714b-4bbb-9acd-75bf277a468a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f3c090ab672790901baae01ae86f8d22e008b4ac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750087"
---
# <a name="smtp-connection-manager"></a><span data-ttu-id="e1d8c-102">Диспетчер соединений SMTP</span><span class="sxs-lookup"><span data-stu-id="e1d8c-102">SMTP Connection Manager</span></span>
  <span data-ttu-id="e1d8c-103">Диспетчер соединений SMTP предоставляет пакету возможность подключения к серверу SMTP (Simple Mail Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="e1d8c-103">An SMTP connection manager enables a package to connect to a Simple Mail Transfer Protocol (SMTP) server.</span></span> <span data-ttu-id="e1d8c-104">Задача "Отправка почты" из состава служб [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] использует диспетчер соединений SMTP.</span><span class="sxs-lookup"><span data-stu-id="e1d8c-104">The Send Mail task that [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] includes uses an SMTP connection manager.</span></span>  
  
 <span data-ttu-id="e1d8c-105">При использовании Microsoft Exchange в качестве SMTP-сервера, возможно, появится необходимость установить конфигурацию диспетчера соединений SMTP для использования проверки подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="e1d8c-105">When using Microsoft Exchange as the SMTP server, you may need to configure the SMTP connection manager to use Windows Authentication.</span></span> <span data-ttu-id="e1d8c-106">Серверы Exchange можно конфигурировать так, чтобы они не разрешали SMTP-сеансы, не прошедшие проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="e1d8c-106">Exchange servers may be configured to not allow unauthenticated SMTP connections.</span></span>  
  
## <a name="configuration-the-smtp-connection-manager"></a><span data-ttu-id="e1d8c-107">Настройка диспетчера соединений SMTP</span><span class="sxs-lookup"><span data-stu-id="e1d8c-107">Configuration the SMTP Connection Manager</span></span>  
 <span data-ttu-id="e1d8c-108">При добавлении к пакету диспетчера соединений SMTP [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] создает диспетчер соединений, который будет разрешен в соединение SMTP во время выполнения, устанавливает свойства диспетчера соединений и добавляет его к коллекции `Connections` пакета.</span><span class="sxs-lookup"><span data-stu-id="e1d8c-108">When you add an SMTP connection manager to a package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that will resolve to an SMTP connection at run time, sets the connection manager properties, and adds the connection manager to the `Connections` collection on the package.</span></span> <span data-ttu-id="e1d8c-109">Свойству `ConnectionManagerType` диспетчера соединений присваивается значение `SMTP`.</span><span class="sxs-lookup"><span data-stu-id="e1d8c-109">The `ConnectionManagerType` property of the connection manager is set to `SMTP`.</span></span>  
  
 <span data-ttu-id="e1d8c-110">Произвести настройку конфигурации диспетчера соединений SMTP можно следующими способами:</span><span class="sxs-lookup"><span data-stu-id="e1d8c-110">You can configure an SMTP connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="e1d8c-111">Указать строку соединения.</span><span class="sxs-lookup"><span data-stu-id="e1d8c-111">Provide a connection string.</span></span>  
  
-   <span data-ttu-id="e1d8c-112">Укажите имя SMTP-сервера.</span><span class="sxs-lookup"><span data-stu-id="e1d8c-112">Specify the name of an SMTP server.</span></span>  
  
-   <span data-ttu-id="e1d8c-113">Выберите метод проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="e1d8c-113">Specify the authentication method to use.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="e1d8c-114">Диспетчер SMTP-соединений поддерживает только анонимную проверку подлинности и проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="e1d8c-114">The SMTP connection manager supports only anonymous authentication and Windows Authentication.</span></span> <span data-ttu-id="e1d8c-115">Обычная проверка подлинности не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="e1d8c-115">It does not support basic authentication.</span></span>  
  
-   <span data-ttu-id="e1d8c-116">Укажите, будет ли отправка сообщений электронной почты шифроваться с использованием протокола SSL.</span><span class="sxs-lookup"><span data-stu-id="e1d8c-116">Specify whether to encrypt communication using Secure Sockets Layer (SSL) when sending e-mail messages.</span></span>  
  
 <span data-ttu-id="e1d8c-117">Значения свойств можно задавать с помощью конструктора [!INCLUDE[ssIS](../../includes/ssis-md.md)] или программными средствами.</span><span class="sxs-lookup"><span data-stu-id="e1d8c-117">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="e1d8c-118">Дополнительные сведения о свойствах, которые можно задавать в конструкторе служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] , см. в статье [Редактор диспетчера SMTP-сеансов](../smtp-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="e1d8c-118">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, see [SMTP Connection Manager Editor](../smtp-connection-manager-editor.md).</span></span>  
  
 <span data-ttu-id="e1d8c-119">Дополнительные сведения о программной настройке диспетчера подключений см. в разделах <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> и [Добавление соединений программным образом](../building-packages-programmatically/adding-connections-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="e1d8c-119">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
  
