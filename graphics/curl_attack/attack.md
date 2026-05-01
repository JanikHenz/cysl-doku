```bash
➜  ~ curl -s -X POST http://localhost:8000/api/v1/auth/register \
-H "Content-Type: application/json" \
-d '{"organization_name":"Opfer GmbH","email":"opfer@test.ch","password":"opfer1234","first_name":"Opfer","last_name":"Opfer"}' \
| python3 -m json.tool
{
    "access_token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJleHAiOjE4MDg5ODM5OTEsInN1YiI6IjYyYmQ2YWZhLTI2N2YtNDQ0NS1hODQyLWM0NzA1YzdhMTczOSIsInR5cGUiOiJhY2Nlc3MiLCJvcmdfaWQiOiI2ZjJmMTE0Ni0xN2IzLTRiMGYtODUzZi00ODI3YzVlZTM0MjEiLCJyb2xlIjoiYWRtaW4ifQ.nGFyldvCw_a2PYoqyI8g3ppMy-7HKMOQUDtakFw6y28",
    "refresh_token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJleHAiOjE4MDg5ODM5OTEsInN1YiI6IjYyYmQ2YWZhLTI2N2YtNDQ0NS1hODQyLWM0NzA1YzdhMTczOSIsInR5cGUiOiJyZWZyZXNoIn0.6Ckb14Y6Wa-KtxxHuUnVCBMN4mOjnnrRDNdtP43g35c",
    "token_type": "bearer",
    "expires_in": 31536000
}
➜  ~ export TOKEN=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJleHAiOjE4MDg5ODM5OTEsInN1YiI6IjYyYmQ2YWZhLTI2N2YtNDQ0NS1hODQyLWM0NzA1YzdhMTczOSIsInR5cGUiOiJhY2Nlc3MiLCJvcmdfaWQiOiI2ZjJmMTE0Ni0xN2IzLTRiMGYtODUzZi00ODI3YzVlZTM0MjEiLCJyb2xlIjoiYWRtaW4ifQ.nGFyldvCw_a2PYoqyI8g3ppMy-7HKMOQUDtakFw6y28
➜  ~ curl -s -X POST http://localhost:8000/api/v1/vehicles \
-H "Authorization: Bearer $TOKEN" \
-H "Content-Type: application/json" \
-d '{"registration_plate":"OPFER-001","make":"Toyota","model":"Camry","year":1992,"type":"suv","fuel_type":"gasoline"}' \
| python3 -m json.tool
{
    "deleted_at": null,
    "created_at": "2026-04-29T07:34:48.031902Z",
    "updated_at": "2026-04-29T07:34:48.031902Z",
    "registration_plate": "OPFER-001",
    "vin": null,
    "make": "Toyota",
    "model": "Camry",
    "year": 1992,
    "type": "suv",
    "fuel_type": "gasoline",
    "status": "active",
    "color": null,
    "current_odometer": "0.00",
    "fuel_capacity": null,
    "image": null,
    "insurance_expiry": null,
    "insurance_provider": null,
    "insurance_policy_number": null,
    "registration_expiry": null,
    "last_service_date": null,
    "next_service_date": null,
    "next_service_odometer": null,
    "notes": null,
    "id": "2dbd498a-e79b-4f71-8d0a-b1e785d7a718",
    "organization_id": "6f2f1146-17b3-4b0f-853f-4827c5ee3421",
    "assigned_employee_id": null,
    "cost_center_id": null,
    "average_fuel_efficiency": null,
    "total_fuel_cost": "0.00",
    "total_maintenance_cost": "0.00"
}
```

```bash
➜  ~ curl -s -X POST http://localhost:8000/api/v1/auth/register \
-H "Content-Type: application/json" \
-d '{"organization_name":"Angreifer GMBH","email":"angreifer@test.ch","password":"angreifer","first_name":"Angreifer","last_name":"Angreifer"}' \
| python3 -m json.tool
{
    "access_token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJleHAiOjE4MDg5ODQxMjQsInN1YiI6IjEzMTNjMzY0LWVkODAtNGQ4OS04ZTA4LTkyZDZkNzRkNTczYyIsInR5cGUiOiJhY2Nlc3MiLCJvcmdfaWQiOiJlOTY2NTJjYi01MjcxLTQ1NDUtYTNkMi04MjU5YjM2THhM2EiLCJyb2xlIjoiYWRtaW4ifQ.K-bQ2hUZDbmDKtR-LoyaC4acJ2WRMkb3VqKqCU37aIw",
    "refresh_token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJleHAiOjE4MDg5ODQxMjQsInN1YiI6IjEzMTNjMzY0LWVkODAtNGQ4OS04ZTA4LTkyZDZkNzRkNTczYyIsInR5cGUiOiJyZWZyZXNoIn0.88-kv5IOgt01gYT57Psio3ajxnK7hxQIgsp8fUXgrDk",
    "token_type": "bearer",
    "expires_in": 31536000
}
➜  ~ export TOKEN=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJleHAiOjE4MDg5ODQxMjQsInN1YiI6IjEzMTNjMzY0LWVkODAtNGQ4OS04ZTA4LTkyZDZkNzRkNTczYyIsInR5cGUiOiJhY2Nlc3MiLCJvcmdfaWQiOiJlOTY2NTJjYi01MjcxLTQ1NDUtYTNkMi04MjU5YjM2THhM2EiLCJyb2xlIjoiYWRtaW4ifQ.K-bQ2hUZDbmDKtR-LoyaC4acJ2WRMkb3VqKqCU37aIw
➜  ~ export VID=2dbd498a-e79b-4f71-8d0a-b1e785d7a718
➜  ~ curl -s -X GET http://localhost:8000/api/v1/vehicles/$VID \
-H "Authorization: Bearer $TOKEN" \
| python3 -m json.tool
{
    "deleted_at": null,
    "created_at": "2026-04-29T07:34:48.031902Z",
    "updated_at": "2026-04-29T07:34:48.031902Z",
    "registration_plate": "OPFER-001",
    "vin": null,
    "make": "Toyota",
    "model": "Camry",
    "year": 1992,
    "type": "suv",
    "fuel_type": "gasoline",
    "status": "active",
    "color": null,
    "current_odometer": "0.00",
    "fuel_capacity": null,
    "image": null,
    "insurance_expiry": null,
    "insurance_provider": null,
    "insurance_policy_number": null,
    "registration_expiry": null,
    "last_service_date": null,
    "next_service_date": null,
    "next_service_odometer": null,
    "notes": null,
    "id": "2dbd498a-e79b-4f71-8d0a-b1e785d7a718",
    "organization_id": "6f2f1146-17b3-4b0f-853f-4827c5ee3421",
    "assigned_employee_id": null,
    "cost_center_id": null,
    "average_fuel_efficiency": null,
    "total_fuel_cost": "0.00",
    "total_maintenance_cost": "0.00"
}
➜  ~ curl -s -X DELETE http://localhost:8000/api/v1/vehicles/$VID \
-H "Authorization: Bearer $TOKEN" \
-w "\nHTTP-Status: %{http_code}\n"

HTTP-Status: 204
➜  ~ curl -s -X GET http://localhost:8000/api/v1/vehicles/$VID \
-H "Authorization: Bearer $TOKEN" \
| python3 -m json.tool
{
    "deleted_at": "2026-04-29T07:40:23.627920Z",
    "created_at": "2026-04-29T07:34:48.031902Z",
    "updated_at": "2026-04-29T07:40:23.620890Z",
    "registration_plate": "OPFER-001",
    "vin": null,
    "make": "Toyota",
    "model": "Camry",
    "year": 1992,
    "type": "suv",
    "fuel_type": "gasoline",
    "status": "active",
    "color": null,
    "current_odometer": "0.00",
    "fuel_capacity": null,
    "image": null,
    "insurance_expiry": null,
    "insurance_provider": null,
    "insurance_policy_number": null,
    "registration_expiry": null,
    "last_service_date": null,
    "next_service_date": null,
    "next_service_odometer": null,
    "notes": null,
    "id": "2dbd498a-e79b-4f71-8d0a-b1e785d7a718",
    "organization_id": "6f2f1146-17b3-4b0f-853f-4827c5ee3421",
    "assigned_employee_id": null,
    "cost_center_id": null,
    "average_fuel_efficiency": null,
    "total_fuel_cost": "0.00",
    "total_maintenance_cost": "0.00"
}
```
