# Bounce logfiles

Log files with the prefix "bounces" hold information about bounced messages.
You can download the content of these files in CSV, JSON, and XML format using the
[REST logfiles API](rest-logfiles) or the dashboard. These log files contain the following
data in the respective order:

| Name        | Description                                                                                                     |
| ----------- | --------------------------------------------------------------------------------------------------------------- |
| id          | The unique id of the message that was bounced                                                                   |
| time        | The time we received the bounce (YYYY-MM-DD hh:mm:ss formatted)                                                 |
| envelope    | The envelope of the message                                                                                     |
| recipient   | The recipient of the message                                                                                    |
| mime        | The mime content of the received bounce                                                                         |
| tags        | The tags of the message that bounced, separated by semicolons                                                   |
| templateid  | The template id that is used for the message that bounced (0 if no template is used or when it isn't available) |

## More information

* [REST non-send calls](./rest-other-calls)
* [REST retrieve events](./rest-events)
