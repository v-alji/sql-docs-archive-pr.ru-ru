---
title: Свойства агента SQL Server (страница "Подключение") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.agent.connection.f1
ms.assetid: d6a677ff-60ad-47ba-a0cb-df4193b165e0
author: stevestein
ms.author: sstein
ms.openlocfilehash: ec9ae575f1ced510d95256d6827435e5b6ad89d1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667527"
---
# <a name="sql-server-agent-properties-connection-page"></a><span data-ttu-id="997b4-102">Свойства агента SQL Server (страница «Соединение»)</span><span class="sxs-lookup"><span data-stu-id="997b4-102">SQL Server Agent Properties (Connection Page)</span></span>
  <span data-ttu-id="997b4-103">Эта страница используется для просмотра и изменения параметров соединения от [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] службы агента к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="997b4-103">Use this page to view and modify the settings for the connection from the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="997b4-104">Варианты</span><span class="sxs-lookup"><span data-stu-id="997b4-104">Options</span></span>  
 <span data-ttu-id="997b4-105">**Псевдоним локального сервера**</span><span class="sxs-lookup"><span data-stu-id="997b4-105">**Alias local host server**</span></span>  
 <span data-ttu-id="997b4-106">Указывает псевдоним, который применяется для подключения к локальному экземпляру [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="997b4-106">Specifies the alias to use to connect to the local instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="997b4-107">Если невозможно использовать параметры соединения для агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] по умолчанию, определите псевдоним для экземпляра и укажите здесь псевдоним.</span><span class="sxs-lookup"><span data-stu-id="997b4-107">If you cannot use the default connection options for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, define an alias for the instance and specify the alias here.</span></span>  
  
 <span data-ttu-id="997b4-108">**Использовать проверку подлинности Windows**</span><span class="sxs-lookup"><span data-stu-id="997b4-108">**Use Windows Authentication**</span></span>  
 <span data-ttu-id="997b4-109">В качестве метода проверки подлинности, используемого для подключения к экземпляру [!INCLUDE[msCoName](../../includes/msconame-md.md)] , устанавливается проверка подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="997b4-109">Sets [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Authentication as the authentication method used to connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="997b4-110">подключается как учетная запись, под которой работает служба агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="997b4-110">Agent connects as the account that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service runs as.</span></span>  
  
 <span data-ttu-id="997b4-111">**Использовать проверку подлинности SQL Server**</span><span class="sxs-lookup"><span data-stu-id="997b4-111">**Use SQL Server Authentication**</span></span>  
 <span data-ttu-id="997b4-112">В качестве метода проверки подлинности, используемого для подключения к экземпляру сервера [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , устанавливается проверка подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="997b4-112">Sets [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication as the authentication method used to connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="997b4-113">поддерживается для обратной совместимости.</span><span class="sxs-lookup"><span data-stu-id="997b4-113">Authentication is provided for backward compatibility.</span></span> <span data-ttu-id="997b4-114">Для повышения безопасности, по возможности, используйте проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="997b4-114">For improved security, use Windows Authentication if possible.</span></span>  
  
 <span data-ttu-id="997b4-115">**Имя входа**</span><span class="sxs-lookup"><span data-stu-id="997b4-115">**Login**</span></span>  
 <span data-ttu-id="997b4-116">Указывается имя входа, используемое для подключения к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="997b4-116">Specifies the login name to use to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="997b4-117">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="997b4-117">**Password**</span></span>  
 <span data-ttu-id="997b4-118">Указывается пароль, используемый для подключения к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="997b4-118">Specifies the password to use to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
  
