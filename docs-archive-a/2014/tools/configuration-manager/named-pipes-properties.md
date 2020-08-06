---
title: Свойства именованных каналов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- pipes [SQL Server]
- listening [SQL Server], pipes
- pipes [SQL Server], listening on pipes
- Named Pipes [SQL Server], listening on pipes
ms.assetid: a5fd5b8e-f889-485b-89e3-d4010ec4c6ec
author: stevestein
ms.author: sstein
ms.openlocfilehash: 80790c1cb8830a0fd132721f375a70d2574421b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659050"
---
# <a name="named-pipes-properties"></a><span data-ttu-id="19758-102">Свойства именованных каналов</span><span class="sxs-lookup"><span data-stu-id="19758-102">Named Pipes Properties</span></span>
  <span data-ttu-id="19758-103">Используйте страницу **Протокол** в диалоговом окне **Named Pipes Properties** (Свойства именованных каналов), чтобы просмотреть или изменить именованный канал, который прослушивается [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], во время использования протокола именованных каналов.</span><span class="sxs-lookup"><span data-stu-id="19758-103">Use the **Protocol**page on the **Named Pipes Properties** dialog box to view or change the named pipe that [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] listens to, when using the Named Pipes protocol.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="19758-104">должен быть перезапущен, чтобы включить протокол, отключить протокол или изменить именованный канал.</span><span class="sxs-lookup"><span data-stu-id="19758-104">must be restarted to enable or disable the protocol, or change the named pipe.</span></span>  
  
## <a name="options"></a><span data-ttu-id="19758-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="19758-105">Options</span></span>  
 <span data-ttu-id="19758-106">**Enabled**</span><span class="sxs-lookup"><span data-stu-id="19758-106">**Enabled**</span></span>  
 <span data-ttu-id="19758-107">Возможные значения: **Да** и **Нет**.</span><span class="sxs-lookup"><span data-stu-id="19758-107">Possible values are **Yes** and **No**.</span></span>  
  
 <span data-ttu-id="19758-108">**Имя канала**</span><span class="sxs-lookup"><span data-stu-id="19758-108">**Pipe Name**</span></span>  
 <span data-ttu-id="19758-109">Указывает именованный канал, который прослушивается [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="19758-109">Specifies the named pipe on which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] listens.</span></span> <span data-ttu-id="19758-110">По умолчанию [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] прослушивает `\\.\pipe\sql\query` для экземпляра по умолчанию и `\\.\pipe\MSSQL$<instancename>\sql\query` для именованного экземпляра.</span><span class="sxs-lookup"><span data-stu-id="19758-110">By default, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] listens on: `\\.\pipe\sql\query` for the default instance and `\\.\pipe\MSSQL$<instancename>\sql\query` for a named instance.</span></span> <span data-ttu-id="19758-111">Длина этого поля ограничена 2047 символами.</span><span class="sxs-lookup"><span data-stu-id="19758-111">This field is limited to 2047 characters.</span></span>  
  
## <a name="creating-an-alternate-named-pipe"></a><span data-ttu-id="19758-112">Создание альтернативного именованного канала</span><span class="sxs-lookup"><span data-stu-id="19758-112">Creating an Alternate Named Pipe</span></span>  
 <span data-ttu-id="19758-113">Чтобы изменить именованный канал, введите новое имя канала в поле **Имя канала** , а затем остановите и перезапустите [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="19758-113">To change the named pipe, type the new pipe name in the **Pipe Name** box and then stop and restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="19758-114">Так как **sql\query** хорошо известен в качестве именованного канала, используемого [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], изменение канала может помочь сократить риск проведения атак вредоносными программами.</span><span class="sxs-lookup"><span data-stu-id="19758-114">Since **sql\query** is well known as the named pipe used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], changing the pipe can help reduce the risk of attack by malicious programs.</span></span>  
  
### <a name="example"></a><span data-ttu-id="19758-115">Пример</span><span class="sxs-lookup"><span data-stu-id="19758-115">Example</span></span>  
 <span data-ttu-id="19758-116">Введите **\\\\.\pipe\unit\app** , чтобы прослушивать канал **unit\app** .</span><span class="sxs-lookup"><span data-stu-id="19758-116">Type **\\\\.\pipe\unit\app** to listen on the **unit\app** pipe.</span></span>  
  
 <span data-ttu-id="19758-117">Введите **\\\\.\pipe\acct** , чтобы прослушивать канал **acct** .</span><span class="sxs-lookup"><span data-stu-id="19758-117">Type **\\\\.\pipe\acct** to listen on the **acct** pipe.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19758-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="19758-118">See Also</span></span>  
 <span data-ttu-id="19758-119">[Включение или отключение сетевого протокола сервера](../../database-engine/configure-windows/enable-or-disable-a-server-network-protocol.md) </span><span class="sxs-lookup"><span data-stu-id="19758-119">[Enable or Disable a Server Network Protocol](../../database-engine/configure-windows/enable-or-disable-a-server-network-protocol.md) </span></span>  
 <span data-ttu-id="19758-120">[Выбор сетевого протокола](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md) </span><span class="sxs-lookup"><span data-stu-id="19758-120">[Choosing a Network Protocol](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md) </span></span>  
 [<span data-ttu-id="19758-121">Создание допустимой строки подключения, использующей протокол именованных каналов</span><span class="sxs-lookup"><span data-stu-id="19758-121">Creating a Valid Connection String Using Named Pipes</span></span>](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-named-pipes.md)  
  
  
