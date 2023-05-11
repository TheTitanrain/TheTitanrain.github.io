---
layout: post
title: Veeam B&R Error RetainShortTerm
---

Ошибка Veeam Backup and Replication при выполнении задания:

Failed to perform applying backup retention for restore point 16.02.2023 2:00:26 Error: Agent: Failed to process method {NasMaster.RetainShortTerm}: Connection was lost, task will be cancelled
Error: Agent: Failed to process method {NasMaster.RetainShortTerm}: Connection was lost, task will be cancelled

или

Failed to perform applying backup retention policy for restore point 8/5/2020 9:00:32 PM Error: Agent: Failed to process method {NasMaster.RetainShortTerm}: Failed to find item 0005
Error: Agent: Failed to process method {NasMaster.RetainShortTerm}: Failed to find item 0005

Задание может работать месяцами, но вдруг такая ошибка.

Решение:
Удерживая клавишу CTRL, щелкните правой кнопкой мыши на задаче и выберите "Start new backup". Это действие начнёт новую цепочку резервных копий. После этого ошибка исчезнет.

Ссылка с решением: https://forums.veeam.com/post388126.html#p388126
