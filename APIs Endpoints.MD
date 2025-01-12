# API Endpoints Documentation

## **1. Items API**

### **Endpoint: `/api/item/`**
- **HTTP Methods**: `GET`, `POST`
- **Description**: List all items or create a new item.
- **Request Parameters**:
  - For `POST`:
    ```json
    {
      "Name": "Item Name",
      "Description": "Item Description",
      "Quantity": 100,
      "Price": 50.0,
      "Category": 1,
      "low_stock_threshold": 10,
      "store": 1,
      "barcode": "12345"
    }
    ```
- **Responses**:
  - `200 OK` (for `GET`): List of all items.
  - `201 Created` (for `POST`): The newly created item.

### **Endpoint: `/api/item/<int:pk>/`**
- **HTTP Methods**: `GET`, `PUT`, `DELETE`
- **Description**: Retrieve, update, or delete a specific item.
- **Request Parameters**:
  - For `PUT`:
    ```json
    {
      "Name": "Updated Name",
      "Description": "Updated Description",
      "Quantity": 50,
      "Price": 40.0,
      "Category": 2,
      "low_stock_threshold": 5,
      "store": 1,
      "barcode": "67890"
    }
    ```
- **Responses**:
  - `200 OK` (for `GET` and `PUT`): Item details or updated item.
  - `204 No Content` (for `DELETE`).

### **Endpoint: `/api/item/level/`**
- **HTTP Method**: `GET`
- **Description**: List inventory levels for all items.
- **Response**:
  ```json
  [
    {
      "id": 1,
      "Name": "Item Name",
      "Quantity": 50
    }
  ]
  ```

### **Endpoint: `/api/item/report/`**
- **HTTP Method**: `GET`
- **Description**: Generate an inventory report.
- **Response**:
  ```json
  {
    "total_items": 10,
    "total_value": 5000.0
  }
  ```

### **Endpoint: `/api/item/barcode/<str:barcode>/`**
- **HTTP Method**: `GET`
- **Description**: Retrieve an item by its barcode.
- **Response**:
  ```json
  {
    "id": 1,
    "Name": "Item Name",
    "Description": "Item Description",
    "Quantity": 100,
    "Price": 50.0,
    "barcode": "12345"
  }
  ```

### **Endpoint: `/api/item/reorder/`**
- **HTTP Method**: `GET`
- **Description**: List items below their reorder threshold.
- **Response**:
  ```json
  [
    {
      "id": 1,
      "Name": "Low Stock Item",
      "Quantity": 5
    }
  ]
  ```

---

## **2. Categories API**

### **Endpoint: `/api/category/`**
- **HTTP Methods**: `GET`, `POST`
- **Description**: List all categories or create a new category.
- **Request Parameters**:
  - For `POST`:
    ```json
    {
      "Name": "Category Name"
    }
    ```
- **Responses**:
  - `200 OK` (for `GET`): List of all categories.
  - `201 Created` (for `POST`): The newly created category.

### **Endpoint: `/api/category/<int:pk>/`**
- **HTTP Methods**: `GET`, `PUT`, `DELETE`
- **Description**: Retrieve, update, or delete a specific category.
- **Responses**:
  - `200 OK` (for `GET` and `PUT`): Category details or updated category.
  - `204 No Content` (for `DELETE`).

---

## **3. Stores API**

### **Endpoint: `/api/stores/`**
- **HTTP Methods**: `GET`, `POST`
- **Description**: List all stores or create a new store.
- **Request Parameters**:
  - For `POST`:
    ```json
    {
      "Name": "Store Name",
      "Location": "Store Location"
    }
    ```
- **Responses**:
  - `200 OK` (for `GET`): List of all stores.
  - `201 Created` (for `POST`): The newly created store.

### **Endpoint: `/api/stores/<int:pk>/`**
- **HTTP Methods**: `GET`, `PUT`, `DELETE`
- **Description**: Retrieve, update, or delete a specific store.
- **Responses**:
  - `200 OK` (for `GET` and `PUT`): Store details or updated store.
  - `204 No Content` (for `DELETE`).

---

## **4. Users API**

### **Endpoint: `/api/users/`**
- **HTTP Methods**: `GET`, `POST`
- **Description**: List all users or create a new user.
- **Request Parameters**:
  - For `POST`:
    ```json
    {
      "username": "user1",
      "email": "user1@example.com",
      "password": "password123"
    }
    ```
- **Responses**:
  - `200 OK` (for `GET`): List of all users.
  - `201 Created` (for `POST`): The newly created user.

### **Endpoint: `/api/users/<int:pk>/`**
- **HTTP Methods**: `GET`, `PUT`, `DELETE`
- **Description**: Retrieve, update, or delete a specific user.
- **Responses**:
  - `200 OK` (for `GET` and `PUT`): User details or updated user.
  - `204 No Content` (for `DELETE`).

---

## **5. Roles API**

### **Endpoint: `/api/roles/`**
- **HTTP Methods**: `GET`, `POST`
- **Description**: List all roles or create a new role.
- **Request Parameters**:
  - For `POST`:
    ```json
    {
      "name": "Role Name",
      "description": "Role Description"
    }
    ```
- **Responses**:
  - `200 OK` (for `GET`): List of all roles.
  - `201 Created` (for `POST`): The newly created role.

### **Endpoint: `/api/roles/<int:pk>/`**
- **HTTP Methods**: `GET`, `PUT`, `DELETE`
- **Description**: Retrieve, update, or delete a specific role.
- **Responses**:
  - `200 OK` (for `GET` and `PUT`): Role details or updated role.
  - `204 No Content` (for `DELETE`).
