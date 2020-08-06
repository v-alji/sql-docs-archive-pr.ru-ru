---
title: Редактор диспетчера FTP-сеансов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.ftpconnectionmanager.f1
helpviewer_keywords:
- FTP Connection Manager Editor
ms.assetid: 874b6585-255b-4a43-8396-bb08c3e8ac2b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d14635a4d90c267801f6d372dda5c7bcc7f4869f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752264"
---
# <a name="ftp-connection-manager-editor"></a><span data-ttu-id="c0106-102">редактор диспетчера FTP-сеансов</span><span class="sxs-lookup"><span data-stu-id="c0106-102">FTP Connection Manager Editor</span></span>
  <span data-ttu-id="c0106-103">Диалоговое окно **Редактор диспетчера FTP-соединений** используется для задания свойств подключения к серверу FTP.</span><span class="sxs-lookup"><span data-stu-id="c0106-103">Use the **FTP Connection Manager Editor** dialog box to specify properties for connecting to an FTP server.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="c0106-104">Диспетчер FTP-соединений поддерживает только анонимную проверку подлинности и обычную проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="c0106-104">The FTP connection manager supports only anonymous authentication and basic authentication.</span></span> <span data-ttu-id="c0106-105">Проверка подлинности Windows не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="c0106-105">It does not support Windows Authentication.</span></span>  
  
 <span data-ttu-id="c0106-106">Дополнительные сведения о диспетчере FTP-сеансов см. в разделе [FTP Connection Manager](connection-manager/ftp-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="c0106-106">To learn more about the FTP connection manager, see [FTP Connection Manager](connection-manager/ftp-connection-manager.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="c0106-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="c0106-107">Options</span></span>  
 <span data-ttu-id="c0106-108">**Имя сервера**</span><span class="sxs-lookup"><span data-stu-id="c0106-108">**Server name**</span></span>  
 <span data-ttu-id="c0106-109">Позволяет задать имя сервера FTP.</span><span class="sxs-lookup"><span data-stu-id="c0106-109">Provide the name of the FTP server.</span></span>  
  
 <span data-ttu-id="c0106-110">**Порт сервера**</span><span class="sxs-lookup"><span data-stu-id="c0106-110">**Server port**</span></span>  
 <span data-ttu-id="c0106-111">Позволяет задать номер порта, используемый для соединения с FTP-сервером.</span><span class="sxs-lookup"><span data-stu-id="c0106-111">Specify the port number on the FTP server to use for the connection.</span></span> <span data-ttu-id="c0106-112">Значение по умолчанию этого свойства равно **21**.</span><span class="sxs-lookup"><span data-stu-id="c0106-112">The default value of this property is **21**.</span></span>  
  
 <span data-ttu-id="c0106-113">**User name**</span><span class="sxs-lookup"><span data-stu-id="c0106-113">**User name**</span></span>  
 <span data-ttu-id="c0106-114">Позволяет задать имя пользователя для доступа к FTP-серверу.</span><span class="sxs-lookup"><span data-stu-id="c0106-114">Provide a user name to access the FTP server.</span></span> <span data-ttu-id="c0106-115">Значение этого свойства по умолчанию равно **anonymous**.</span><span class="sxs-lookup"><span data-stu-id="c0106-115">The default value of this property is **anonymous**.</span></span>  
  
 <span data-ttu-id="c0106-116">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="c0106-116">**Password**</span></span>  
 <span data-ttu-id="c0106-117">Позволяет задать пароль для доступа к серверу FTP.</span><span class="sxs-lookup"><span data-stu-id="c0106-117">Provide the password to access the FTP server.</span></span>  
  
 <span data-ttu-id="c0106-118">**Время ожидания (сек)**</span><span class="sxs-lookup"><span data-stu-id="c0106-118">**Time-out (in seconds)**</span></span>  
 <span data-ttu-id="c0106-119">Укажите число секунд, в течение которых задача займет время ожидания. Значение **0** указывает на бесконечное количество времени.</span><span class="sxs-lookup"><span data-stu-id="c0106-119">Specify the number of seconds the task takes before timing out. A value of **0** indicates an infinite amount of time.</span></span> <span data-ttu-id="c0106-120">Значение по умолчанию этого свойства равно **60**.</span><span class="sxs-lookup"><span data-stu-id="c0106-120">The default value of this property is **60**.</span></span>  
  
 <span data-ttu-id="c0106-121">**Использовать пассивный режим**</span><span class="sxs-lookup"><span data-stu-id="c0106-121">**Use passive mode**</span></span>  
 <span data-ttu-id="c0106-122">Позволяет указать сторону, инициирующую соединение, — сервер или клиент.</span><span class="sxs-lookup"><span data-stu-id="c0106-122">Specify whether the server or the client initiates the connection.</span></span> <span data-ttu-id="c0106-123">В активном режиме соединение инициируется сервером, а в пассивном режиме — клиентом.</span><span class="sxs-lookup"><span data-stu-id="c0106-123">The server initiates the connection in active mode, and the client activates the connection in passive mode.</span></span> <span data-ttu-id="c0106-124">По умолчанию, установлен **активный режим**.</span><span class="sxs-lookup"><span data-stu-id="c0106-124">The default value of this property is **active mode**.</span></span>  
  
 <span data-ttu-id="c0106-125">**Повторы**</span><span class="sxs-lookup"><span data-stu-id="c0106-125">**Retries**</span></span>  
 <span data-ttu-id="c0106-126">Позволяет задать число попыток соединения, осуществляемых задачей.</span><span class="sxs-lookup"><span data-stu-id="c0106-126">Specify the number of times the task attempts to make a connection.</span></span> <span data-ttu-id="c0106-127">Значение **0** указывает на отсутствие ограничений на число попыток.</span><span class="sxs-lookup"><span data-stu-id="c0106-127">A value of **0** indicates no limit to the number of attempts.</span></span>  
  
 <span data-ttu-id="c0106-128">**Размер фрагмента данных (КБ)**</span><span class="sxs-lookup"><span data-stu-id="c0106-128">**Chunk size (in KB)**</span></span>  
 <span data-ttu-id="c0106-129">Позволяет задать размер фрагмента передаваемых данных в килобайтах.</span><span class="sxs-lookup"><span data-stu-id="c0106-129">Provide a chunk size in kilobytes for transmitting data.</span></span>  
  
 <span data-ttu-id="c0106-130">**Проверка соединения**</span><span class="sxs-lookup"><span data-stu-id="c0106-130">**Test Connection**</span></span>  
 <span data-ttu-id="c0106-131">После настройки диспетчера FTP-соединений следует проверить доступность подключения, нажав кнопку **Проверить соединение**.</span><span class="sxs-lookup"><span data-stu-id="c0106-131">After configuring the FTP Connection Manager, confirm that the connection is viable by clicking **Test Connection**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0106-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="c0106-132">See Also</span></span>  
 [<span data-ttu-id="c0106-133">Справочник по сообщениям об ошибках служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="c0106-133">Integration Services Error and Message Reference</span></span>](../../2014/integration-services/integration-services-error-and-message-reference.md)  
  
  
