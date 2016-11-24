+++
title = "UpdateClientAddon"
toc = true
+++

Updates a Client Addon

### Request Parameters

| Parameter | Type | Description | Required |
| --------- | ---- | ----------- | -------- |
| action | string | "UpdateClientAddon" | Required |
| id | int | The id of the client addon to update | Required |
| status | string | The status to change the addon to | Optional |
| terminationDate | \Carbon\Carbon | The termination date of the addon Y-m-d | Optional |
| addonid | int | The configured addon id to update the client addon to | Optional |
| name | string | The custom name to apply to the addon | Optional |
| setupfee | float | The setup fee for the client addon | Optional |
| recurring | float | The recurring amount for the client addon | Optional |
| billingcycle | string | The billing cycle for the addon | Optional |
| nextduedate | \Carbon\Carbon | The next due date for the addon Y-m-d | Optional |
| nextinvoicedate | \Carbon\Carbon | The next invoice date for the addon Y-m-d | Optional |
| terminationDate | \Carbon\Carbon | The termination date of the addon Y-m-d | Optional |
| notes | string | The admin notes to associate with the addon | Optional |

### Response Parameters

| Parameter | Type | Description |
| --------- | ---- | ----------- |
| result | string | The result of the operation: success or error |
| id | int | The Id of the updated addon |


### Example Request (CURL)

```
$ch = curl_init();
curl_setopt($ch, CURLOPT_URL, 'https://www.example.com/includes/api.php');
curl_setopt($ch, CURLOPT_POST, 1);
curl_setopt($ch, CURLOPT_POSTFIELDS,
    http_build_query(
        array(
            'action' => 'UpdateClientAddon',
            'username' => 'ADMIN_USERNAME',
            'password' => 'ADMIN_PASSWORD',
            'id' => '1',
            'status' => 'Terminated',
            'responsetype' => 'json',
        )
    )
);
$response = curl_exec($ch);
curl_close($ch);
```


### Example Request (Local API)

```
$command = 'UpdateClientAddon';
$postData = array(
    'id' => '1',
    'status' => 'Terminated',
);
$adminUsername = 'ADMIN_USERNAME';

$results = localAPI($command, $postData, $adminUsername);
print_r($results);
```


### Example Response JSON

```
{
    "result": "success",
    "id": "1"
}
```


### Error Responses

Possible error condition responses include:

* Addon ID Not Found
* Nothing to Update


### Version History

| Version | Changelog |
| ------- | --------- |
| 1.0 | Initial Version |