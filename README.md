# 🔐 Authentication (Login System) - Simple Notes

## 📌 Authentication Services (Kaam karne wale tools)
Authentication ka matlab hota hai: **user kaun hai, ye check karna**. Jab user login karta hai, tab hum uski identity verify karte hain.

Iske liye commonly 3 cheezein use hoti hain:

- **JWT (JSON Web Token)** – Token based login system  
- **Session** – Server pe data store hota hai  
- **Cookies** – Browser ke andar chhota data store hota hai (like session_id)

---

## 🔄 Do Tarah ke Authentication Hote Hain

### 1. **Stateful Authentication**  
_(Session / Cookie based)_

🧠 "Stateful" ka matlab hota hai **server ya memory mein user ka data rakhna** (jaise: name, email, session ID).

#### ⚙ Kaise kaam karta hai?
1. User login karta hai
2. Server ek **session create** karta hai
3. User ka data (name, email) **memory mein store** karta hai
4. Ek **session_id** browser ke cookie mein bhejta hai
5. Har baar jab user request karega, ye session_id bhejega
6. Server memory se verify karega

#### ✔ Features:
- Short time login ke liye best
- Server ko sab control hota hai
- Lekin server ki memory lagti hai

---

### 2. **Stateless Authentication (JWT)**  
_(Token based)_

🧠 "Stateless" ka matlab hai **server kuch store nahi karta**, sab kuch client ke pass (browser/mobile) hota hai.

#### ⚙ Kaise kaam karta hai?
1. User login karta hai
2. Server ek **JWT token** banata hai
3. Token ke andar hota hai: `id`, `name`, `email`, `role`
4. Is token ko **secret key se sign** karta hai
5. Ye token browser ke local storage ya cookie mein store hota hai
6. Har request ke saath client ye token bhejta hai
7. Server bas token verify karta hai, memory use nahi karta

#### ✔ Features:
- Server memory use nahi karta
- Fast & secure (if implemented correctly)
- APIs aur mobile apps ke liye perfect

---

## 🧾 Easy Comparison Table

| Feature             | Stateful (Session/Cookie)    | Stateless (JWT)               |
|---------------------|------------------------------|-------------------------------|
| Server memory use?  | Haan (yes)                   | Nahi (no)                     |
| Speed               | Thoda slow (due to memory)   | Fast                          |
| Control             | Server ke pass full control  | Token ke through control      |
| Best for            | Simple login/logout websites | Mobile apps, APIs, SPAs       |

---

## 🔚 Summary

- **Stateful (Session/Cookie)**: Server sab kuch yaad rakhta hai. Best for small websites.
- **Stateless (JWT)**: Server kuch nahi rakhta, sab kuch token mein hota hai. Best for scalable systems like mobile apps, React/Vue apps, APIs.

