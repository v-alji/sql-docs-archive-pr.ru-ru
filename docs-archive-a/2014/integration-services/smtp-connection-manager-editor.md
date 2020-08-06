---
title: Редактор диспетчера SMTP-соединений | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.smtpconnection.f1
helpviewer_keywords:
- SMTP Connection Manager Editor
ms.assetid: 2693de0d-b04d-4325-a856-ce667d2b8aa1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e14ed49f64b9faca40f575fc6760a8d25c0d4573
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751247"
---
# <a name="smtp-connection-manager-editor"></a><span data-ttu-id="c9a5c-102">редактор диспетчера SMTP-сеансов</span><span class="sxs-lookup"><span data-stu-id="c9a5c-102">SMTP Connection Manager Editor</span></span>
  <span data-ttu-id="c9a5c-103">Используйте диалоговое окно **Редактор диспетчера SMTP-сеансов** для задания SMTP-сервера.</span><span class="sxs-lookup"><span data-stu-id="c9a5c-103">Use the **SMTP Connection Manager Editor** dialog box to specify a Simple Mail Transfer Protocol (SMTP) server.</span></span>  
  
 <span data-ttu-id="c9a5c-104">Дополнительные сведения о диспетчере SMTP-соединений см. в разделе [SMTP Connection Manager](connection-manager/smtp-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="c9a5c-104">To learn more about the SMTP connection manager, see [SMTP Connection Manager](connection-manager/smtp-connection-manager.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="c9a5c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c9a5c-105">Options</span></span>  
 <span data-ttu-id="c9a5c-106">**имя**;</span><span class="sxs-lookup"><span data-stu-id="c9a5c-106">**Name**</span></span>  
 <span data-ttu-id="c9a5c-107">Задает уникальное имя диспетчера соединений.</span><span class="sxs-lookup"><span data-stu-id="c9a5c-107">Provide a unique name for the connection manager.</span></span>  
  
 <span data-ttu-id="c9a5c-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="c9a5c-108">**Description**</span></span>  
 <span data-ttu-id="c9a5c-109">Задайте описание диспетчера соединений.</span><span class="sxs-lookup"><span data-stu-id="c9a5c-109">Describe the connection manager.</span></span> <span data-ttu-id="c9a5c-110">Рекомендуется описать назначение диспетчера соединений, чтобы сделать пакеты самодокументируемыми и более простыми в использовании.</span><span class="sxs-lookup"><span data-stu-id="c9a5c-110">As a best practice, describe the connection manager in terms of its purpose, to make packages self-documenting and easier to maintain.</span></span>  
  
 <span data-ttu-id="c9a5c-111">**SMTP-сервер**</span><span class="sxs-lookup"><span data-stu-id="c9a5c-111">**SMTP server**</span></span>  
 <span data-ttu-id="c9a5c-112">Позволяет задать имя сервера SMTP.</span><span class="sxs-lookup"><span data-stu-id="c9a5c-112">Provide the name of the SMTP server.</span></span>  
  
 <span data-ttu-id="c9a5c-113">**Использовать проверку подлинности Windows**</span><span class="sxs-lookup"><span data-stu-id="c9a5c-113">**Use Windows Authentication**</span></span>  
 <span data-ttu-id="c9a5c-114">Выберите для отправки почты с помощью SMTP-сервера, который использует проверку подлинности Windows для доступа к серверу.</span><span class="sxs-lookup"><span data-stu-id="c9a5c-114">Select to send mail using an SMTP server that uses Windows Authentication to authenticate access to the server.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="c9a5c-115">Диспетчер SMTP-соединений поддерживает только анонимную проверку подлинности и проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="c9a5c-115">The SMTP connection manager supports only anonymous authentication and Windows Authentication.</span></span> <span data-ttu-id="c9a5c-116">Обычная проверка подлинности не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="c9a5c-116">It does not support basic authentication.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c9a5c-117">При использовании Microsoft Exchange в качестве SMTP-сервера может потребоваться задать для параметра **использовать проверку подлинности Windows** значение `True` .</span><span class="sxs-lookup"><span data-stu-id="c9a5c-117">When using Microsoft Exchange as the SMTP server, you may need to set **Use Windows Authentication** to `True`.</span></span> <span data-ttu-id="c9a5c-118">Серверы Exchange можно настроить так, чтобы они запрещали использовать соединения SMTP, не прошедшие проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="c9a5c-118">Exchange servers may be configured to disallow unauthenticated SMTP connections.</span></span>  
  
 <span data-ttu-id="c9a5c-119">**Включить протокол SSL**</span><span class="sxs-lookup"><span data-stu-id="c9a5c-119">**Enable Secure Sockets Layer (SSL)**</span></span>  
 <span data-ttu-id="c9a5c-120">Выберите, чтобы отправляемые почтовые сообщения шифровались по протоколу SSL.</span><span class="sxs-lookup"><span data-stu-id="c9a5c-120">Select to encrypt communication using Secure Sockets Layer (SSL) when sending e-mail messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9a5c-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="c9a5c-121">See Also</span></span>  
 [<span data-ttu-id="c9a5c-122">Справочник по сообщениям об ошибках служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="c9a5c-122">Integration Services Error and Message Reference</span></span>](../../2014/integration-services/integration-services-error-and-message-reference.md)  
  
  
