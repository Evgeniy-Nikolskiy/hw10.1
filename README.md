# Homework 10.1

## Ответ на вопрос 1

Очевидный набор метрик:  
### CPU
CPU usage %  
Load Average %   
CPU System/User/IOwait/Idle
### Memory
RAM total
RAM used
RAM free
### Processes
Blocked I/O
Running
### статистика Load Balancer
TargetResponseTime_Average
ActiveConnectionCount_Average


Так как по задаче взаимодействие осуществляется по http можно добавить проверку статуса:
nginx status
php-fpm
memcached status

### HTTPCode
HTTPCode_Target_2XX_Count_Average  
HTTPCode_Target_3XX_Count_Average  
HTTPCode_Target_4XX_Count_Average  
HTTPCode_Target_5XX_Count_Average  

## Ответ на вопрос 2
Менеджеру можно предложить придерживаться SLA, SLO и SLI. 
Определится с возможностями компании и какой уровень сервиса можно предложить конечному пользователю. Составить соглашение на юридической основе

Развернуто описать метрики понятным языком, что за какие механизмы отвичает и отслеживает

Использовать не только внутренний сбор метрик, но и внешний(black box) чтобы иметь больше информации что происходит на стороне клиента.

## Ответ на вопрос 3
Можно использовать облачный сбор логов:
Loggly  
SumoLogic  
Splunk  
Papertrail  
Logz.io  
Timber  
Logentries  
Logsene  

## Ответ на вопрос 4
Ошибка заключается в неполном сборе информации о кодах ответа:  
SLI = (summ_2xx_requests + summ_3xx_requests + summ_4xx_requests + summ_5xx_requests)/(summ_all_requests)