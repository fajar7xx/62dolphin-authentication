# 62dolphin
  62dolphin microservice is a REST API writter in Golang designed for authenticaction with Json Web Token

  Created by 62teknologi.com, perfected by Community.

## Catalog
This introduction will help You explain the concept and characteristic of catalog.

### Concept

Catalog is a collection of data, for example; products, articles, galleries.

In the context of a 62whale, a catalog would refer to a collection of `User Defined Data` that has certain `Information`, `Behaviors`, `Associations` and `Characteristic`.

You will learn how to define data on later section.

### Information
- Must Have ID
- Must Have Slug
- Must Have Created At
- Must Have Updated At
- Must Have Deleted At

### Behaviors
- can be created
- can be retrieved
- can be updated
- can be deleted

### Associations
- may has one category
- may has many items
- may has many to many groups
- may has many comments
- may belong to certain user 


## Running 62whale

Follow the instruction below to running 62whale on Your local machine.

### Prerequisites
Make sure to have preinstalled this prerequisites apps before You continue to installation manual. we don't include how to install these apps below most of this prerequisites is a free apps which You can find the "How to" installation tutorial anywhere in web and different machine OS have different way to install.
- MySql
- Go

### Installation manual
This installation manual will guide You to running the binary on Your ubuntu or mac terminal.

1. Clone the repository
```
git clone https://github.com/62teknologi/62dolphin.git
```

2. Change directory to the cloned repository
```
cd 62dolphin
```

3. Initiate the submodule
```
git submodule update --init
```

3. tidy
```
go mod tidy
```

4. Create .env base on .env.example
```
cp .env.example .env
```

5. setup env file like this
```
ENVIRONMENT=development
DB_SOURCE_1=user:db_pass@tcp(db_ip:db_port)/db_name?charset=utf8mb4&parseTime=True&loc=Local
DB_SOURCE_2=
HTTP_SERVER_ADDRESS=0.0.0.0:7001
MONOLITH_URL=http://localhost:8001
API_KEY=

FIREBASE_CONFIG_PATH=

TOKEN_SYMMETRIC_KEY=12345678901234567890123456789012
ACCESS_TOKEN_DURATION=24h
REFRESH_TOKEN_DURATION=87h
```

6. Build the binary
```
go build -v -o 62dolphin main.go
```

7. Run the server
```
./62dolphin
```

The API server will start running on `http://localhost:7001`. You can now interact with the API using Your preferred API client or through the command line with `curl`.

## API Endpoints

### Retrieve Catalog by id

#### Endpoint
```
GET /api/v1/catalog/:name/:id
```

### Retrieve Catalog List

#### Endpoint
```
GET /api/v1/catalog/:name
```

#### Parameter
| Name | Def | Description |
| - | - | - |
| page | 1 | return response in pagination format, eg: ```page=1``` will return first page of the response    |
| per_page | 30 | set how many data per pagination response |
| search | null | filter response by string |
| order | 1 | order data by one or multiple field, eg: ```order=name+asc``` or ```order[]=name+asc&order[]=created_at+desc```    |
| :field | null | filter specific column You want, eg: if Your catalog have ```user_id``` field then You can add ```user_id=1``` to params for searching all catalog where user_id is 1. it support multi value by sending ```user_id[]``` instead ```user_id``` |

### Create Catalog

#### Endpoint
```
POST /api/v1/catalog/:name
```

#### Parameter
| Name | Def | Description |
| - | - | - |
| :field | null | field You want to insert |
| groups[] | null | lorem |
| items[] | null | lorem |


### Update Catalog

#### Endpoint
```
PUT /api/v1/catalog/:name/:id
```

#### Parameter
| Name | Def | Description |
| - | - | - |
| :field | null | field You want to insert |
| groups[] | null | lorem |

### Delete Catalog

#### Endpoint
```
DEL /api/v1/catalog/:name/:id
```
# Set Up a Catalog
- WIP   

## Generate Catalog
- WIP

## Set Information
- WIP

## Set Validation
- WIP

## Set Associations
- WIP

## Set Filterable
- WIP

## Set Summary
- WIP

## Set Operation
- WIP

# Contributing

If You'd like to contribute to the development of the 62whale REST API, please follow these steps:

1. Fork the repository
2. Create a new branch for Your feature or bugfix
3. Commit Your changes to the branch
4. Create a pull request, describing the changes You've made

We appreciate Your contributions and will review Your pull request as soon as possible.

## Must Preserve Characteristic 
- Reduce repetition
- Easy to use REST API
- Easy to setup
- Easy to Customizable
- high performance
- Robust data validation and error handling
- Well documented API endpoints

## License

This project is licensed under the MIT License. For more information, please see the [LICENSE](./LICENSE) file.

# About 62
**E.nam\Du.a**

Indonesian language; spelling: A-num\Due-wa

Origin: Enam Dua means ‘six-two’ or sixty two. It is Indonesia’s international country code (+62), that was also used as a meme word for “Indonesia” by “Indonesian internet citizen” (netizen) in social media.