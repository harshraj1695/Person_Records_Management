# 📁 Person Records Management in C (File + Linked List)

## 📌 Overview

This C application provides functionality to **manage person records** using both **file I/O** and a **linked list**. It supports storing, retrieving, searching, and deleting person data efficiently.

---

## 🧾 Record Format

Each **person record** contains the following fields:

- `id` (int): Unique identifier  
- `name` (string): Full name (supports spaces)  
- `age` (int): Age of the person  
- `salary` (int): Salary value  
- `email` (string): Email address

### 📄 File Storage Format

Records are stored in the file with the following colon-separated format:

```
id:name:age:salary:email
```

#### Example:

```
1:John Doe:30:50000:john@example.com
```

---

## 🧱 Data Structures

### 1. `Person`

Represents an individual record.

```c
typedef struct {
    int id;
    char name[50];
    int age;
    int salary;
    char email[100];
} Person;
```

---

### 2. `Node`

Represents a node in the linked list, holding a `Person` and a pointer to the next node.

```c
typedef struct Node {
    Person p;
    struct Node* next;
} Node;
```

---

## 🛠️ Functionalities

### 1. `Node* add_person(const char* filename, Person p, Node* head)`

Adds a new person record to both the linked list and the file.

- **Parameters:**
  - `filename`: Name of the file to append to.
  - `p`: The person to be added.
  - `head`: Pointer to the current head of the list.
- **Returns:**
  - Updated head pointer of the list.

---

### 2. `void read_from_file(const char* filename)`

Reads and prints all person records directly from the file.

- **Parameters:**
  - `filename`: The name of the file to read from.
- **Output:**
  - Formatted print of all records in the file.

---

### 3. `void read_list(Node* head)`

Prints all records stored in the linked list.

- **Parameters:**
  - `head`: Pointer to the head of the linked list.
- **Output:**
  - Displays each person's data if the list is not empty.

---

### 4. `Node* load_list(const char* filename)`

Loads all file-stored records into a linked list in memory.

- **Parameters:**
  - `filename`: File containing the person records.
- **Returns:**
  - Head pointer to the newly built list.

---

### 5. `int idsize(Node* head)`

Calculates the number of records in the linked list.

- **Parameters:**
  - `head`: Head pointer of the linked list.
- **Returns:**
  - Total node count (int).

---

### 6. `Person* search(Node* head, int idd)`

Searches the linked list for a person by ID.

- **Parameters:**
  - `head`: Head pointer of the list.
  - `idd`: ID to search for.
- **Returns:**
  - Pointer to the found `Person` or `NULL` if not found.

---

### 7. `Node* deletedata(Node* head, const char* filename, int id_to_delete)`

Deletes a person record from both the linked list and the file.

- **Parameters:**
  - `head`: Head pointer of the list.
  - `filename`: Name of the file.
  - `id_to_delete`: ID of the person to remove.
- **Process:**
  - Removes the node from memory.
  - Rewrites the file, omitting the deleted record.
- **Returns:**
  - Updated head pointer of the list.

---



## 📂 File Example: `people.txt`

```
1:John Doe:30:50000:john@example.com
2:Alice Smith:28:55000:alice@example.com
```

---

## 📎 Notes

- The file must be writable and readable.
- Names with spaces are supported using `scanf(" %[^
]s", name);`.
- Ensure proper memory handling to avoid leaks in larger applications.

---

## 📘 License

MIT License (if applicable)

---

## 👨‍💻 Author

**Harsh Raj** – [GitHub Profile](https://github.com/harshraj1695)
