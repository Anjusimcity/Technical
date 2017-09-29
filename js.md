When a variable is not present, undefined will be displayed in UI. To prevent it include || condition and print empty String as below.

      htmlText += '<td style="width:300px;"> <a href="#" onclick="javascript:handleEvent( +
                    (processName || " ")';
