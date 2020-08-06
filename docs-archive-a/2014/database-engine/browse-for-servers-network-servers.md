---
title: Обзор серверов (сетевые серверы) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.browseservers.network.f1
ms.assetid: a59ffcd6-4b69-4c5c-9740-699ccb2183fb
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 0ba5e4e5dd6d9a6541a98e0cb30229d7335bac24
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665591"
---
# <a name="browse-for-servers-network-servers"></a><span data-ttu-id="30c8e-102">Обзор серверов (сетевые серверы)</span><span class="sxs-lookup"><span data-stu-id="30c8e-102">Browse for Servers (Network Servers)</span></span>
  <span data-ttu-id="30c8e-103">Если при подключении к компоненту [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] неизвестно точное имя экземпляра [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], в поле **Имя сервера** нажмите кнопку **Продолжить обзор**, чтобы открыть диалоговое окно **Выбор серверов**.</span><span class="sxs-lookup"><span data-stu-id="30c8e-103">If you are connecting to a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] component and you do not know the exact name of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance, click **Browse for more** in the **Server name** box to open the **Browse for Servers** dialog box.</span></span>  
  
 <span data-ttu-id="30c8e-104">Это диалоговое окно заполняется службой « [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , браузер» на серверах.</span><span class="sxs-lookup"><span data-stu-id="30c8e-104">This dialog is populated by the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Browser service on the server computers.</span></span> <span data-ttu-id="30c8e-105">Название экземпляра может не появиться в списке по нескольким причинам, перечисленным ниже.</span><span class="sxs-lookup"><span data-stu-id="30c8e-105">There are several reasons why the name of an instance might not appear in the list:</span></span>  
  
-   <span data-ttu-id="30c8e-106">Служба « [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , браузер» может не работать на компьютере с запущенным [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="30c8e-106">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Browser service might not be running on the computer running [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="30c8e-107">Возможно, порт UDP 1434 заблокирован брандмауэром.</span><span class="sxs-lookup"><span data-stu-id="30c8e-107">UDP port 1434 might be blocked by a firewall.</span></span>  
  
-   <span data-ttu-id="30c8e-108">Возможно, установлен флаг **HideInstance** .</span><span class="sxs-lookup"><span data-stu-id="30c8e-108">The **HideInstance** flag might be set.</span></span>  
  
 <span data-ttu-id="30c8e-109">Чтобы подключиться к экземпляру, который не появился в списке, введите полную строку соединения для экземпляра, включая номер порта TCP/IP или имя канала именованных каналов.</span><span class="sxs-lookup"><span data-stu-id="30c8e-109">To connect to an instance that does not appear in the list, type a full connection string for the instance, including the TCP/IP port number or the named pipes pipe name.</span></span>  
  
## <a name="options"></a><span data-ttu-id="30c8e-110">Варианты</span><span class="sxs-lookup"><span data-stu-id="30c8e-110">Options</span></span>  
 <span data-ttu-id="30c8e-111">**Выберите экземпляр SQL Server в сети для соединения**</span><span class="sxs-lookup"><span data-stu-id="30c8e-111">**Select a SQL Server instance in the network for your connection**</span></span>  
 <span data-ttu-id="30c8e-112">Укажите сервер, с которым нужно соединиться, выбрав экземпляр [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , показанный в дереве.</span><span class="sxs-lookup"><span data-stu-id="30c8e-112">Designate the server you want to connect to by clicking on the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance displayed in the tree.</span></span> <span data-ttu-id="30c8e-113">Можно отобразить или скрыть части древовидного представления, щелкнув узлы, помеченные **+** **-** символом или.</span><span class="sxs-lookup"><span data-stu-id="30c8e-113">You can show or hide portions of the tree view by clicking on the nodes marked with a **+** or **-** symbol.</span></span>  
  
  
