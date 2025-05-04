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
# 5 User Authentication Methods
1. Password-based authentication

   - Passwords are the most common methods of authentication. Passwords can be in the form of a string of letters, numbers, or special characters. To protect yourself you need to create strong passwords that       
      include a combination of all possible options. 

2. Multi-factor authentication

   - requires two or more independent ways to identify a user. Examples include codes generated from the user’s smartphone, Captcha tests, fingerprints, voice biometrics or facial recognition. 

3. Certificate-based authentication

   -  Certificate-based authentication technologies identify users, machines or devices by using digital certificates. A digital certificate is an electronic document based on the idea of a driver’s license or         a passport. 

      The certificate contains the digital identity of a user including a public key, and the digital signature of a certification authority. Digital certificates prove the ownership of a public key and issued         only by a certification authority. 

      Users provide their digital certificates when they sign in to a server. The server verifies the credibility of the digital signature and the certificate authority. The server then uses cryptography to             confirm that the user has a correct private key associated with the certificate.

4. Biometric authentication

   - Biometrics authentication is a security process that relies on the unique biological characteristics of an individual. Here are key advantages of using biometric authentication technologies:

      Biological characteristics can be easily compared to authorized features saved in a database. 
      Biometric authentication can control physical access when installed on gates and doors. 
      You can add biometrics into your multi-factor authentication process.
      Biometric authentication technologies are used by consumers, governments and private corporations including airports, military bases, and national borders. The technology is increasingly adopted due to           the ability to achieve a high level of security without creating friction for the user. Common biometric authentication methods include:

      Facial recognition—matches the different face characteristics of an individual trying to gain access to an approved face stored in a database. Face recognition can be inconsistent when comparing faces at         different angles or comparing people who look similar, like close relatives.
      Fingerprint scanners
      Speaker Recognition
      Eye scanners—include technologies like iris recognition and retina scanners. Iris scanners project a bright light towards the eye and search for unique patterns in the colored ring around the pupil of the       eye. The patterns are then compared to approved information stored in a database. Eye-based authentication may suffer inaccuracies if a person wears glasses or contact lenses.
     
5. Token-based authentication

   - Token-based authentication technologies enable users to enter their credentials once and receive a unique encrypted string of random characters in exchange. You can then use the token to access protected         systems instead of entering your credentials all over again. The digital token proves that you already have access permission. Use cases of token-based authentication include RESTful APIs that are used by       multiple frameworks and clients.

