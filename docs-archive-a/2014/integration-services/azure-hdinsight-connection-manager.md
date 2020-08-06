---
title: Диспетчер подключений Azure HDInsight | Документы Майкрософт
ms.custom: ''
ms.date: 02/28/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- SQL12.DTS.DESIGNER.AFPHDICM.F1
- SQL11.DTS.DESIGNER.AFPHDICM.F1
ms.assetid: 850a978d-5dba-45b6-a10e-306aafbc353d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0eaf2f57fec50a58ad1b7e7578407fb6cf3fa0c0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728650"
---
# <a name="azure-hdinsight-connection-manager"></a><span data-ttu-id="95017-102">Диспетчер подключений Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="95017-102">Azure HDInsight Connection Manager</span></span>
<span data-ttu-id="95017-103">**Диспетчер подключений Azure HDInsight** позволяет пакету служб SSIS подключаться к кластеру Azure HDInsight.</span><span class="sxs-lookup"><span data-stu-id="95017-103">The **Azure HDInsight Connection Manager** enables an SSIS package to connect to an Azure HDInsight cluster.</span></span>

<span data-ttu-id="95017-104">Чтобы создать и настроить **диспетчер подключений Azure HDInsight**, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="95017-104">To create and configure an **Azure HDInsight Connection Manager**, follow the steps below:</span></span>

1. <span data-ttu-id="95017-105">В диалоговом окне **Добавление диспетчера соединений со службами SSIS** выберите **AzureHDInsight** и щелкните **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="95017-105">In the **Add SSIS Connection Manager** dialog box, select **AzureHDInsight**, and click **Add**.</span></span>
2. <span data-ttu-id="95017-106">В диалоговом окне **Редактор диспетчера подключений Azure HDInsight** укажите **DNS-имя кластера** (без префикса протокола), **имя пользователя** и **пароль** для кластера HDInsight, к которому необходимо подключиться.</span><span class="sxs-lookup"><span data-stu-id="95017-106">In the **Azure HDInsight Connection Manager Editor** dialog box, specify the **Cluster DNS name** (without the protocol prefix), **Username**, and **Password** for the HDInsight cluster to connect to.</span></span>
3. <span data-ttu-id="95017-107">Чтобы закрыть диалоговое окно, нажмите кнопку **ОК** .</span><span class="sxs-lookup"><span data-stu-id="95017-107">Click **OK** to close the dialog box.</span></span>
4. <span data-ttu-id="95017-108">Свойства созданного диспетчера соединений можно просмотреть в окне **Свойства** .</span><span class="sxs-lookup"><span data-stu-id="95017-108">You can see the properties of the connection manager you created in the **Properties** window.</span></span>
