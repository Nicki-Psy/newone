# newone
<!DOCTYPE html>
<html>
    <head>
        <title>My Project </title>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
        <script src="http://login2explore.com/jpdb/resources/js/0.0.3/jpdb-commons.js"></script>
    </head>
    <body align=" center">
    <h2>Update Data</h2>
    Username:<input type=" text" placeholder=" enter the username" id=" username"/><br><br>
    Password:<input type=" password" placehoder=" enter the password" name=" password"/><br><br>
    <input type="submit" value="Login"/>

<script>
        function executeCommand(reqString, dbBaseUrl, apiEndPointUrl)
         {
            var url = dbBaseUrl + apiEndPointUrl;
            var jsonObj;
            $.post(url, reqString, function (result) {
                jsonObj = JSON.parse(result);
            }).fail(function (result)
             {
                var dataJsonObj = result.responseText;
                jsonObj = JSON.parse(dataJsonObj);
            });
            return jsonObj;
        }

  function updateData()
        {
            var token =" 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";
var dbname ="pi_db";
            var relationName = " root";

var Username = (document.getElementById("username").value);
            var Password = document.getElementByname("password").value;
            
            var jsonObj = {
                Password : password,
            };

     var reqString = createUPDATERecordRequest(token, JSON.stringify(jsonObj), dbname, relationName, Username);
            alert(reqString);
            jQuery.ajaxSetup({async: false});
            var resultObj = executeCommand(reqString,
                    "http://api.login2explore.com:5577", "/api/iml");
            jQuery.ajaxSetup({async: true});
            alert(JSON.stringify(resultObj));
            
        }
    </script>

</body>
</html>
