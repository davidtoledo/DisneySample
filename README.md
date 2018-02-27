**Create Ticket Order**
----
  Creates a ticket order on disneyworld.com

* **URL**

  /tickets/add

* **Method:**

  `POST`
  
*  **URL Params**

   **Required:**
 
   `name=[String]`
   `email=[String]`
   `address=[String]`
   `type=[Integer]`
   `creditCard=[String]`

* **Data Params**

  None

* **Success Response:**

  * **Code:** 200 <br />
    **Content:** `{ id : 12, name : "Michael Bloom" }`
 
* **Error Response:**

  * **Code:** 404 NOT FOUND <br />
    **Content:** `{ error : "User doesn't exist" }`

  OR

  * **Code:** 401 UNAUTHORIZED <br />
    **Content:** `{ error : "You are unauthorized to make this request." }`

* **Sample Call:**

  ```javascript
    $.ajax({
      url: "/users/1",
      dataType: "json",
      type : "GET",
      success : function(r) {
        console.log(r);
      }
    });
  ```
