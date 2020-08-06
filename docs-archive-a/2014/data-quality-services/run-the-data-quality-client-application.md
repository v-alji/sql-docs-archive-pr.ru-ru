---
title: Запуск клиентского приложения Data Quality Client | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
f1_keywords:
- sql12.dqs.browseforservers.f1
- sql12.dqs.connecttoserver.f1
ms.assetid: 0b2aa202-7ab2-4c9d-b0f1-802588053a1e
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 45372ce22fd1b18f0ec13f7a7fd76a369b78dfd6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751508"
---
# <a name="run-the-data-quality-client-application"></a><span data-ttu-id="595f5-102">Запуск клиентского приложения DQS</span><span class="sxs-lookup"><span data-stu-id="595f5-102">Run the Data Quality Client Application</span></span>
  <span data-ttu-id="595f5-103">Чтобы использовать [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS), следует запустить клиент [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] и войти на сервер [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].</span><span class="sxs-lookup"><span data-stu-id="595f5-103">You can use [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) by running [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)], and logging on to a [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="595f5-104">Перед началом</span><span class="sxs-lookup"><span data-stu-id="595f5-104">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="595f5-105">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="595f5-105">Prerequisites</span></span>  
 <span data-ttu-id="595f5-106">Необходимо, чтобы установка сервера [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] , запускаемая с помощью файла DQSInstaller.exe, была завершена.</span><span class="sxs-lookup"><span data-stu-id="595f5-106">You must have completed the [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] installation by running the DQSInstaller.exe file.</span></span> <span data-ttu-id="595f5-107">Дополнительные сведения см. в разделе [Запуск файла DQSInstaller.exe для завершения установки сервера служб DQS](install-windows/run-dqsinstaller-exe-to-complete-data-quality-server-installation.md).</span><span class="sxs-lookup"><span data-stu-id="595f5-107">For more information, see [Run DQSInstaller.exe to Complete Data Quality Server Installation](install-windows/run-dqsinstaller-exe-to-complete-data-quality-server-installation.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="595f5-108">безопасность</span><span class="sxs-lookup"><span data-stu-id="595f5-108">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="595f5-109">Permissions</span><span class="sxs-lookup"><span data-stu-id="595f5-109">Permissions</span></span>  
 <span data-ttu-id="595f5-110">Для входа на сервер [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)]необходимо иметь одну из трех ролей DQS (dqs_adminstrator, dqs_kb_editor или dqs_kb_operator) в базе данных DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="595f5-110">You must have one of the three DQS roles (dqs_adminstrator, dqs_kb_editor, or dqs_kb_operator) granted on the DQS_MAIN database to be able to log on to [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].</span></span>  
  
##  <a name="run-data-quality-client"></a><a name="Run"></a><span data-ttu-id="595f5-111">Запустить Data Quality Client</span><span class="sxs-lookup"><span data-stu-id="595f5-111">Run Data Quality Client</span></span>  
 <span data-ttu-id="595f5-112">Чтобы запустить клиент [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] на компьютере, где он установлен, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="595f5-112">To run [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] on the computer where you have installed it, proceed as follows:</span></span>  
  
1.  <span data-ttu-id="595f5-113">Нажмите кнопку **Пуск**, выберите **Все программы**, затем **[!INCLUDE[ssCurrent](../includes/sscurrent-md.md)]**, затем **Службы Data Quality Services**, затем **Data Quality Client**.</span><span class="sxs-lookup"><span data-stu-id="595f5-113">Click **Start**, point to **All Programs**, click **[!INCLUDE[ssCurrent](../includes/sscurrent-md.md)]**, click **Data Quality Services**, and then click **Data Quality Client**.</span></span>  
  
2.  <span data-ttu-id="595f5-114">В диалоговом окне **Подключение к серверу** выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="595f5-114">In the **Connect to Server** dialog box:</span></span>  
  
    1.  <span data-ttu-id="595f5-115">Укажите сервер, к которому требуется подключить приложение [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="595f5-115">Specify the server that you want to connect the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] application to.</span></span> <span data-ttu-id="595f5-116">Выберите **(LOCAL)** для подключения к [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="595f5-116">Select **(LOCAL)** to connect to [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] on the local computer.</span></span> <span data-ttu-id="595f5-117">Можно также щелкнуть стрелку вниз и выбрать **\<Browse network for more servers>** для подключения к другому серверу (или для подключения к локальному серверу по имени).</span><span class="sxs-lookup"><span data-stu-id="595f5-117">You can also click the down arrow and select **\<Browse network for more servers>** to connect to a different server (or to connect to the local server by name).</span></span> <span data-ttu-id="595f5-118">Открывается диалоговое окно **Обзор серверов** .</span><span class="sxs-lookup"><span data-stu-id="595f5-118">The **Browse for Servers** dialog box will be displayed.</span></span> <span data-ttu-id="595f5-119">Вы можете выбрать сервер на вкладках **Локальные серверы** или **Сетевые серверы** .</span><span class="sxs-lookup"><span data-stu-id="595f5-119">You can select a server in the **Local Servers** tab or in the **Network Servers** tab.</span></span>  
  
    2.  <span data-ttu-id="595f5-120">Чтобы зашифровать передачу данных между сервером [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] и клиентом [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)], щелкните **Параметры**, а затем установите флажок **Шифровать соединение**.</span><span class="sxs-lookup"><span data-stu-id="595f5-120">If you want to encrypt data transfer between [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] and [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)], click **Options**, and then select the **Encrypt Connection** check box.</span></span>  
  
3.  <span data-ttu-id="595f5-121">Нажмите кнопку **Подключиться**.</span><span class="sxs-lookup"><span data-stu-id="595f5-121">Click **Connect**.</span></span>  
  
 <span data-ttu-id="595f5-122">Открывается на главном экране клиента [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="595f5-122">The [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen appears.</span></span> <span data-ttu-id="595f5-123">Дополнительные сведения см. в статье [Главный экран клиента DQS](../../2014/data-quality-services/data-quality-client-home-screen.md).</span><span class="sxs-lookup"><span data-stu-id="595f5-123">For more information, see [Data Quality Client Home Screen](../../2014/data-quality-services/data-quality-client-home-screen.md).</span></span>  
  
  
