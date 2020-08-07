---
title: Параметры электронной почты — Configuration Manager (собственный режим служб SSRS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.rsconfigtool.emailsettings.f1
helpviewer_keywords:
- SQL11.rsconfigtool.emailsettings.F1
ms.assetid: cdad1529-bfa6-41fb-9863-d9ff1b802577
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 8c5f276f8d6566e052ee291118eb1d1c12fbddc9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732438"
---
# <a name="e-mail-settings---configuration-manager-ssrs-native-mode"></a>Параметры электронной почты — диспетчер конфигурации (службы Reporting Services в собственном режиме)
  Эта страница позволяет задать параметры протокола SMTP, предназначенные для доставки отчетов по электронной почте с сервера отчетов. Модуль доставки электронной почты позволяет распространять отчеты и уведомления об их обработке через электронные подписки. Для модуля доставки электронной почты сервера отчетов требуется SMTP-сервер и адрес электронной почты для использования в поле «От».  
  
 Дополнительные параметры могут использоваться для дальнейшей настройки подписок, доставляемых электронной почтой, включая параметры, ограничивающие узлы почтового сервера и доступность модулей подготовки отчетов. Эти параметры нельзя задать в диспетчере конфигурации служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]. Чтобы настроить дополнительные параметры, необходимо вручную изменить файл RSReportServer.config. Дополнительные сведения см. в разделе [Настройка сервера отчетов для доставки электронной почты &#40;SSRS Configuration Manager&#41;](../../sql-server/install/configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager.md) и [Reporting Services файлы конфигурации](../report-server/reporting-services-configuration-files.md) в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] электронной документации по.  
  
 Чтобы открыть эту страницу, запустите диспетчер конфигурации служб Reporting Services и щелкните **Параметры электронной почты** в области навигации. Дополнительные сведения см. в разделе [Использование диспетчера конфигурации служб Reporting Services (собственный режим)](../../sql-server/install/reporting-services-configuration-manager-native-mode.md).  
  
 [!INCLUDE[applies](../../includes/applies-md.md)][!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Собственный режим.  
  
## <a name="options"></a>Параметры  
 **Адрес отправителя**  
 Указывает адрес электронной почты для поля «От» создаваемого сообщения. Необходимо указать учетную запись, имеющую разрешение на передачу почтовых сообщений из SMTP-сервера.  
  
 **Текущий метод доставки SMTP**  
 Указывает, что электронная почта сервера отчетов направляется через SMTP-сервер. Это единственный метод доставки, который можно указать в диспетчере конфигурации служб Reporting Services.  
  
 Альтернативным методом доставки является использование локального каталога считывания службы SMTP. Можно использовать этот метод доставки, если сетевая служба SMTP недоступна. Чтобы указать локальный каталог считывания службы SMTP, необходимо отредактировать файл конфигурации RSReportServer.config. Если вы изменяете файл конфигурации для использования локального каталога службы SMTP, диспетчер конфигурации служб Reporting Services устанавливает для параметра **метода доставки** значение *Custom* , чтобы указать, что в файле конфигурации указан метод доставки.  
  
 В файле конфигурации метод доставки задается параметром `SendUsing`. Дополнительные сведения об указании `SendUsing` параметра см. в разделе [Настройка сервера отчетов для доставки электронной почты &#40;SSRS Configuration Manager&#41;](../../sql-server/install/configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager.md).  
  
 **SMTP-сервер**  
 Укажите используемый SMTP-сервер или шлюз. Можно использовать локальный сервер или SMTP-сервер.  
  
## <a name="see-also"></a>См. также:  
 [Настройка сервера отчетов для доставки электронной почты &#40;Configuration Manager SSRS&#41;](../../sql-server/install/configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager.md)   
 [Диспетчер конфигурации служб Reporting Services разделы справки F1 &#40;служб SSRS в собственном режиме&#41;](../../sql-server/install/reporting-services-configuration-manager-f1-help-topics-ssrs-native-mode.md)  
  
  
