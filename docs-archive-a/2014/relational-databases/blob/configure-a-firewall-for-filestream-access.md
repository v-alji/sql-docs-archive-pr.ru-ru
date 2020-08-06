---
title: Настройка брандмауэра для доступа к FILESTREAM | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- Windows Firewall [Database Engine], FILESTREAM
- FILESTREAM [SQL Server], Windows Firewall
ms.assetid: fc52007f-c26f-4f8e-b9d8-55a7978f4d56
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8b787403fefdd336dd82bf7ccb93cdf21fe5a90d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667243"
---
# <a name="configure-a-firewall-for-filestream-access"></a><span data-ttu-id="5f6d8-102">Настройка брандмауэра для доступа FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="5f6d8-102">Configure a Firewall for FILESTREAM Access</span></span>
  <span data-ttu-id="5f6d8-103">Чтобы использовать FILESTREAM в среде, защищенной брандмауэром, как клиент, так и сервер должны быть в состоянии разрешать имена DNS для сервера, содержащего файлы FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="5f6d8-103">To use FILESTREAM in a firewall-protected environment, both the client and server must be able to resolve DNS names to the server that contains the FILESTREAM files.</span></span> <span data-ttu-id="5f6d8-104">Для данных FILESTREAM требуется, чтобы были открыты порты 139 и 445 для общего доступа к файлам Windows.</span><span class="sxs-lookup"><span data-stu-id="5f6d8-104">FILESTREAM requires the Windows file-sharing ports 139 and 445 to be open.</span></span>  
  
### <a name="to-open-the-windows-file-sharing-ports-on-a-computer-that-is-running-windows-7"></a><span data-ttu-id="5f6d8-105">Открытие портов общего доступа к файлам Windows на компьютере под управлением Windows 7</span><span class="sxs-lookup"><span data-stu-id="5f6d8-105">To open the Windows file-sharing ports on a computer that is running Windows 7</span></span>  
  
1.  <span data-ttu-id="5f6d8-106">На панели управления откройте элемент **Брандмауэр Windows**.</span><span class="sxs-lookup"><span data-stu-id="5f6d8-106">In Control Panel, open **Windows Firewall**.</span></span>  
  
2.  <span data-ttu-id="5f6d8-107">На левой панели нажмите кнопку **Дополнительные параметры**.</span><span class="sxs-lookup"><span data-stu-id="5f6d8-107">In the left pane, click **Advanced settings**.</span></span> <span data-ttu-id="5f6d8-108">Если появится запрос на ввод или подтверждение пароля администратора, введите пароль или подтвердите его.</span><span class="sxs-lookup"><span data-stu-id="5f6d8-108">If you're prompted for an administrator password or confirmation, type the password or provide confirmation.</span></span>  
  
3.  <span data-ttu-id="5f6d8-109">На левой панели окна **Брандмауэр Windows в режиме повышенной безопасности** щелкните раздел **Правила для входящих подключений**, затем на правой панели выберите пункт **Создать правило**.</span><span class="sxs-lookup"><span data-stu-id="5f6d8-109">In the **Windows Firewall with Advanced Security** dialog box, in the left pane, click **Inbound Rules**, and then, in the right pane, click **New Rule**.</span></span>  
  
4.  <span data-ttu-id="5f6d8-110">Чтобы добавить TCP-порт 139, следуйте инструкциям мастера создания правила для нового входящего подключения.</span><span class="sxs-lookup"><span data-stu-id="5f6d8-110">Follow the instructions in the New Inbound Rule wizard to add TCP port 139.</span></span>  
  
5.  <span data-ttu-id="5f6d8-111">Повторите предыдущий шаг для добавления TCP-порта 445.</span><span class="sxs-lookup"><span data-stu-id="5f6d8-111">Repeat the previous step to add TCP port 445.</span></span>  
  
6.  <span data-ttu-id="5f6d8-112">Закройте диалоговое окно **Брандмауэр Windows в режиме повышенной безопасности** .</span><span class="sxs-lookup"><span data-stu-id="5f6d8-112">Close the **Windows Firewall with Advanced Security** dialog box.</span></span>  
  
  
