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


Response :

-   Success

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


-   Error

json
{
    "meta": {
        "code": 500,
        "status": "error",
        "message": "Something went wrong"
    },
}

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

<!-- ============= SEARCH DATA DOKTER END ============= -->

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

<!-- ============= SEARCH DATA DOKTER END ============= -->

