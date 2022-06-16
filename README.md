# proyek-akhirku

<!-- ============= REGISTER START ============= -->
## <a name="register"></a>Register
#### <a name="r_pasien"></a>Register Pasien

Request :

-   Method : POST
-   Endpoint : 'http://127.0.0.1:8000/api/register'
-   Header :
    -   Content-Type : application/json
-   Body
```
json
{
    "name": "example name",
    "email": "example@gmail.com",
    "password": "example_password",
    
    "password_confirmation": "example_password"
    "no_tlp": "example_telepon"
    "jenis_kelamin": "example_jenis_kelamin"
    "alamat": "example_alamat"
}
```
Response :

-   Success
```
json
{
  "meta": {
    "code": 200,
    "status": "success",
    "message": "User Registered"
  },
  "data": {
    "access_token": "example_token",
    "token_type": "Bearer",
    "user": {
      "id": user_id,
      "name": "example name",
      "email": "example@gmail.com",
      "password": "example_password",
      "password_confirmation": "example_password",
      "no_tlp": "example_telepon",
      "jenis_kelamin": "example_jenis_kelamin",
      "alamat": "example_alamat",
      "roles": "USER",
      "created_at": "2022-06-15T02:28:25.000000Z",
      "updated_at": "2022-06-15T02:28:25.000000Z"
    }
  }
}
```

-   Error
```
json
{
    "meta": {
        "code": 500,
        "status": "error",
        "message": "Something went wrong"
    },
}
```
<!-- ============= REGISTER END ============= -->

<!-- ============= GET DATA DOKTER START ============= -->
## <a name="data dokter"></a>Data Dokter
#### <a name="get_datadokter"></a>Data Dokter

Request :

-   Method : GET
-   Endpoint : 'http://127.0.0.1:8000/api/dokter'
-   Header :
    -   Content-Type : application/json
    -   Authorization : Bearer 

Response :

-   Success
```
json
{
  "meta": {
    "code": 200,
    "status": "success",
    "message": "Data dokter berhasil diambil"
  },
  "data": {
    "current_page": 1,
    "data": [
      {
        "id": 1,
        "nama_dokter": "dokter_exampel",
        "photo_dokter": "photo_exampel",
        "bidang_dokter": "bidang_dokter_exampel",
        "created_at": "2022-06-14T15:09:08.000000Z",
        "updated_at": "2022-06-14T15:09:08.000000Z",
        "code": "A",
        "hari_praktek": [
          {
            "id": 1,
            "dokter_id": id_dokter_exampel,
            "hari_praktek": "hari_exampel",
            "created_at": "2022-06-14T15:09:18.000000Z",
            "updated_at": "2022-06-14T15:09:18.000000Z",
            "jampraktek": [
              {
                "id": 1,
                "hari_praktek_id": hari_praktek_id_exampel,
                "jam_praktek": "jam_praktek_exampel",
                "shift": "pagi",
                "created_at": "2022-06-14T15:09:34.000000Z",
                "updated_at": "2022-06-14T15:09:34.000000Z"
              },
              {
                "id": 2,
                "hari_praktek_id": 1,
                "jam_praktek": "17.00 - 22.00",
                "shift": "malam",
                "created_at": "2022-06-14T15:09:42.000000Z",
                "updated_at": "2022-06-14T15:09:42.000000Z"
              }
            ]
          },
          {
            "id": 2,
            "dokter_id": 1,
            "hari_praktek": "selasa",
            "created_at": "2022-06-14T15:09:23.000000Z",
            "updated_at": "2022-06-14T15:09:23.000000Z",
            "jampraktek": []
          }
        ]
      }
    ],
    "first_page_url": "http://127.0.0.1:8000/api/dokter?page=1",
    "from": 1,
    "last_page": 1,
    "last_page_url": "http://127.0.0.1:8000/api/dokter?page=1",
    "links": [
      {
        "url": null,
        "label": "&laquo; Previous",
        "active": false
      },
      {
        "url": "http://127.0.0.1:8000/api/dokter?page=1",
        "label": "1",
        "active": true
      },
      {
        "url": null,
        "label": "Next &raquo;",
        "active": false
      }
    ],
    "next_page_url": null,
    "path": "http://127.0.0.1:8000/api/dokter",
    "per_page": 10,
    "prev_page_url": null,
    "to": 1,
    "total": 1
  }
}
```
<!-- ============= GET DATA DOKTER END ============= -->

<!-- ============= SEARCH DATA DOKTER START ============= -->
## <a name="search data dokter"></a>Search Data Dokter
#### <a name="search_datadokter"></a>Search Data Dokter

Request :

-   Method : GET
-   Endpoint : 'http://127.0.0.1:8000/api/dokter?nama_dokter=name_dokter_example'
-   Header :
    -   Authorization : Bearer 
-   Params :
    -   nama_dokter : name_dokter_example

Response :

-   Success
```
json
{
  "meta": {
    "code": 200,
    "status": "success",
    "message": "Data dokter berhasil diambil"
  },
  "data": {
    "current_page": 1,
    "data": [
      {
        "id": 1,
        "nama_dokter": "name_dokter_example",
        "photo_dokter": "1655219348.jpg",
        "bidang_dokter": "Dokter Umum",
        "created_at": "2022-06-14T15:09:08.000000Z",
        "updated_at": "2022-06-14T15:09:08.000000Z",
        "code": "A",
        "hari_praktek": [
          {
            "id": 1,
            "dokter_id": 1,
            "hari_praktek": "senin",
            "created_at": "2022-06-14T15:09:18.000000Z",
            "updated_at": "2022-06-14T15:09:18.000000Z",
            "jampraktek": [
              {
                "id": 1,
                "hari_praktek_id": 1,
                "jam_praktek": "06.00 - 07.00",
                "shift": "pagi",
                "created_at": "2022-06-14T15:09:34.000000Z",
                "updated_at": "2022-06-14T15:09:34.000000Z"
              },
              {
                "id": 2,
                "hari_praktek_id": 1,
                "jam_praktek": "17.00 - 22.00",
                "shift": "malam",
                "created_at": "2022-06-14T15:09:42.000000Z",
                "updated_at": "2022-06-14T15:09:42.000000Z"
              }
            ]
          },
          {
            "id": 2,
            "dokter_id": 1,
            "hari_praktek": "selasa",
            "created_at": "2022-06-14T15:09:23.000000Z",
            "updated_at": "2022-06-14T15:09:23.000000Z",
            "jampraktek": []
          }
        ]
      }
    ],
    "first_page_url": "http://127.0.0.1:8000/api/dokter?page=1",
    "from": 1,
    "last_page": 1,
    "last_page_url": "http://127.0.0.1:8000/api/dokter?page=1",
    "links": [
      {
        "url": null,
        "label": "&laquo; Previous",
        "active": false
      },
      {
        "url": "http://127.0.0.1:8000/api/dokter?page=1",
        "label": "1",
        "active": true
      },
      {
        "url": null,
        "label": "Next &raquo;",
        "active": false
      }
    ],
    "next_page_url": null,
    "path": "http://127.0.0.1:8000/api/dokter",
    "per_page": 10,
    "prev_page_url": null,
    "to": 1,
    "total": 1
  }
}
```
<!-- ============= SEARCH DATA DOKTER END ============= -->

<!-- ============= DETAIL DATA DOKTER START ============= -->
## <a name="search data dokter"></a>Detail Data Dokter
#### <a name="search_datadokter"></a>Detail Data Dokter

Request :

-   Method : GET
-   Endpoint : 'http://127.0.0.1:8000/api/dokter/1'
-   Header :
    -   Authorization : Bearer 

Response :

-   Success
```
json
{
    "meta": {
        "code": 200,
        "status": "success",
        "message": "Data dokter berhasil diambil"
    },
    "data": {
        "id": 1,
        "nama_dokter": "Dr. Suryadinata",
        "photo_dokter": "1655281603.jpg",
        "bidang_dokter": "Dokter Umum",
        "created_at": "2022-06-15T08:26:43.000000Z",
        "updated_at": "2022-06-15T08:26:43.000000Z",
        "code": "A",
        "hari_praktek": [
            {
                "id": 1,
                "dokter_id": 1,
                "hari_praktek": "senin",
                "created_at": "2022-06-15T08:26:55.000000Z",
                "updated_at": "2022-06-15T08:26:55.000000Z",
                "jampraktek": [
                    {
                        "id": 1,
                        "hari_praktek_id": 1,
                        "jam_praktek": "06.00 - 07.00",
                        "shift": "pagi",
                        "created_at": "2022-06-15T08:27:19.000000Z",
                        "updated_at": "2022-06-15T08:27:19.000000Z"
                    },
                    {
                        "id": 2,
                        "hari_praktek_id": 1,
                        "jam_praktek": "17.00 - 22.00",
                        "shift": "malam",
                        "created_at": "2022-06-15T08:27:31.000000Z",
                        "updated_at": "2022-06-15T08:27:31.000000Z"
                    }
                ]
            },
            {
                "id": 2,
                "dokter_id": 1,
                "hari_praktek": "selasa",
                "created_at": "2022-06-15T08:27:04.000000Z",
                "updated_at": "2022-06-15T08:27:04.000000Z",
                "jampraktek": [
                    {
                        "id": 3,
                        "hari_praktek_id": 2,
                        "jam_praktek": "06.00 - 07.00",
                        "shift": "pagi",
                        "created_at": "2022-06-15T08:31:17.000000Z",
                        "updated_at": "2022-06-15T08:31:17.000000Z"
                    },
                    {
                        "id": 4,
                        "hari_praktek_id": 2,
                        "jam_praktek": "17.00 - 22.00",
                        "shift": "malam",
                        "created_at": "2022-06-15T08:31:31.000000Z",
                        "updated_at": "2022-06-15T08:31:31.000000Z"
                    }
                ]
            }
        ]
    }
}
```
<!-- ============= DETAIL DATA DOKTER END ============= -->

<!-- ============= PENDAFTARAN START ============= -->
## <a name="search data dokter"></a>Pendaftaran
#### <a name="search_datadokter"></a>Pendaftaran

Request :

-   Method : POST
-   Endpoint : 'http://127.0.0.1:8000/api/pendaftaran'
-   Header :
    -   Authorization : Bearer 
    -   Accept : application/json
-   Body
```
json
{
    "dokter_id": "example dokter_id",
    "jam_praktek_id": "example_jam_praktek_id",
    "shiff": "example_shiff",
    "tanggal_pendaftaran": "tanggal_pendaftaran_password"
    "transaksi": "example_transaksi"
    "keluhan": "example_keluhan"
}
```
Response :

-   Success
```
json
{
    "meta": {
        "code": 200,
        "status": "success",
        "message": "Successfully Registed"
    },
    "data": {
        "dokter_id": "1",
        "jam_praktek_id": "1",
        "shiff": "pagi",
        "tanggal_pendaftaran": "2022-06-15",
        "transaksi": "BPJS",
        "keluhan": "Sakit Tipes",
        "user_id": 4,
        "updated_at": "2022-06-16T17:50:10.000000Z",
        "created_at": "2022-06-16T17:50:10.000000Z",
        "id": 9,
        "antrian": "A-002",
        "dokter": {
            "id": 1,
            "nama_dokter": "Dr. Suryadinata",
            "photo_dokter": "1655281603.jpg",
            "bidang_dokter": "Dokter Umum",
            "created_at": "2022-06-15T08:26:43.000000Z",
            "updated_at": "2022-06-15T08:26:43.000000Z",
            "code": "A"
        }
    }
}
```
-   Error
```
json
{
    "meta": {
        "code": 401,
        "status": "error",
        "message": "Form Validation Error !!!"
    },
}
```
<!-- ============= PENDAFTARAN END ============= -->


<!-- ============= ANTRIAN SAYA START ============= -->
## <a name="search data dokter"></a>Antrian Saya
#### <a name="search_datadokter"></a>Antrian Saya

Request :

-   Method : GET
-   Endpoint : 'http://127.0.0.1:8000/api/antrian'
-   Header :
    -   Authorization : Bearer 
    -   Accept : application/json

Response :

-   Success
```
json
{
    "meta": {
        "code": 200,
        "status": "success",
        "message": "Data antrian successfully loaded."
    },
    "data": [
        {
            "id": 9,
            "user_id": 4,
            "dokter_id": 1,
            "jam_praktek_id": 1,
            "shiff": "pagi",
            "tanggal_pendaftaran": "2022-06-15",
            "transaksi": "BPJS",
            "antrian": "A-002",
            "keluhan": "Sakit Tipes",
            "created_at": "2022-06-16T17:50:10.000000Z",
            "updated_at": "2022-06-16T17:50:10.000000Z",
            "dokter": {
                "id": 1,
                "nama_dokter": "Dr. Suryadinata",
                "photo_dokter": "1655281603.jpg",
                "bidang_dokter": "Dokter Umum",
                "created_at": "2022-06-15T08:26:43.000000Z",
                "updated_at": "2022-06-15T08:26:43.000000Z",
                "code": "A"
            },
            "jam_praktek": {
                "id": 1,
                "hari_praktek_id": 1,
                "jam_praktek": "06.00 - 07.00",
                "shift": "pagi",
                "created_at": "2022-06-15T08:27:19.000000Z",
                "updated_at": "2022-06-15T08:27:19.000000Z"
            }
        }
    ]
}
```
<!-- ============= ANTRIAN SAYA END ============= -->

<!-- ============= ANTRIAN SAAT INI START ============= -->
## <a name="search data dokter"></a>Antrian Saat ini
#### <a name="search_datadokter"></a>Antrian Saat ini

Request :

-   Method : GET
-   Endpoint : 'http://127.0.0.1:8000/api/antrian?now=true'
-   Header :
    -   Authorization : Bearer 
    -   Accept : application/json
-   Params:
    -   now : true

Response :

-   Success
```
json
{
  "meta": {
    "code": 200,
    "status": "success",
    "message": "Data antrian successfully loaded."
  },
  "data": [
    {
      "dokter_id": 1,
      "antrian": "A-002",
      "dokter": {
        "id": 1,
        "nama_dokter": "Dr. Suryadinata",
        "photo_dokter": "1655219348.jpg",
        "bidang_dokter": "Dokter Umum",
        "created_at": "2022-06-14T15:09:08.000000Z",
        "updated_at": "2022-06-14T15:09:08.000000Z",
        "code": "A"
      },
      "jam_praktek": null
    }
  ]
}
```
<!-- ============= ANTRIAN SAAT INI END ============= -->

<!-- ============= RIWAYAT START ============= -->
## <a name="search data dokter"></a>Riwayat
#### <a name="search_datadokter"></a>Riwayat

Request :

-   Method : GET
-   Endpoint : 'http://127.0.0.1:8000/api/register'
-   Header :
    -   Authorization : Bearer 
    -   Accept : application/json

Response :

-   Success
```
json
{
    "meta": {
        "code": 200,
        "status": "success",
        "message": "Data antrian successfully loaded."
    },
    "data": [
        {
            "id": 1,
            "user_id": 4,
            "dokter_id": 1,
            "jam_praktek_id": 1,
            "shiff": "pagi",
            "tanggal_pendaftaran": "2022-06-15",
            "transaksi": "BPJS",
            "antrian": "A-001",
            "keluhan": "Sakit Tipes",
            "status": "1",
            "created_at": "2022-06-15T02:16:16.000000Z",
            "updated_at": "2022-06-15T02:16:16.000000Z",
            "dokter": {
                "id": 1,
                "nama_dokter": "Dr. Suryadinata",
                "photo_dokter": "1655281603.jpg",
                "bidang_dokter": "Dokter Umum",
                "created_at": "2022-06-15T08:26:43.000000Z",
                "updated_at": "2022-06-15T08:26:43.000000Z",
                "code": "A"
            },
            "jam_praktek": {
                "id": 1,
                "hari_praktek_id": 1,
                "jam_praktek": "06.00 - 07.00",
                "shift": "pagi",
                "created_at": "2022-06-15T08:27:19.000000Z",
                "updated_at": "2022-06-15T08:27:19.000000Z"
            }
        }
    ]
}
```
<!-- ============= RIWAYAT END ============= -->
