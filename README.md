**Create Ticket Order**
----
  Creates a ticket order on disneyworld.com

* **URL**

  /tickets/add

* **Method:**

  `POST`
  
*  **URL Params**
   
   None
   
* **Data Params**

  { ticket : { name : [string], email : [string], address : [string] type : [string], creditCard : [string] } }

* **Success Response:**

  * **Code:** 201 <br />
  **Content:** `{ id : 5032, msg : "Ticket Successfully Created" }`
 
* **Error Response:**

  * **Code:** 422 Unprocessable Entry <br />
    **Content:** `{ error : "Invalid input data" }`

  OR

  * **Code:** 401 UNAUTHORIZED <br />
    **Content:** `{ error : "You are not allowed to make this request." }`

* **Sample Call:**

  ```javascript
    $.ajax({
      url: "/tickets/add",
      dataType: "json",
      type : "POST",
      data: { 
        ticket: { 
          id      : 5034,
          email   : "email@disney.com" ,
          address : "2023 Grand Oak DR",
          type    : "ORDER",
          creditCard : "ec331f5dd1c5f40e28ea541caec913f6"
        },
      success : function(r) {
        console.log(r);
      }
    });
  ```

**Retrieve Ticket Data**
----
  Returns data about a specific ticket on disneyworld.com

* **URL**

  /tickets/:id

* **Method:**

  `GET`
  
*  **URL Params**

   **Required:**
 
   `id=[integer]`

* **Data Params**

  None

* **Success Response:**

  * **Code:** 200 <br />
    **Content:** `{ id : [integer], name : [string], email : [string], address: [string], type : [string] }`
 
* **Error Response:**

  * **Code:** 404 NOT FOUND <br />
    **Content:** `{ error : "Ticket does not exist" }`

  OR

  * **Code:** 401 UNAUTHORIZED <br />
    **Content:** `{ error : "You are not allowed to make this request." }`

* **Sample Call:**

  ```javascript
    $.ajax({
      url: "/tickets/5034",
      dataType: "json",
      type : "GET",
      success : function(r) {
        console.log(r);
      }
    });
  ```

