Summer Internship 2026 whole project Link : https://github.com/Nandini-Bhimineni/Raritone-Project-Backend

A scalable and modular backend system developed for the **Raritone virtual fashion platform** using Node.js, Express.js, MongoDB, and Cloudinary.

The project provides authentication, product management, user management, virtual try‑on support, avatar management, order processing, and future AI integration capabilities.

---

## Project Overview

Raritone is a virtual fashion platform designed to improve online shopping experiences through:

- **Personalized Shopping** – Body measurements, preferences, and wishlist.
- **Virtual Try‑On Support** – Upload images and preview garments.
- **Avatar Management** – Prepare for AI‑generated 3D avatars.
- **Product Recommendations** – ProductMapping schema for future AI.
- **User Measurements** – Chest, waist, hip, height, shoulder.
- **AI‑Ready Architecture** – Socket.IO, mock endpoints, scalable design.

---

## Technology Stack

| Category          | Technologies |
|-------------------|--------------|
| **Backend**       | Node.js, Express.js |
| **Database**      | MongoDB, Mongoose ODM |
| **Authentication**| JWT, bcrypt, Google OAuth |
| **Cloud Services**| Cloudinary, Multer, Sharp |
| **Security**      | Helmet, Rate Limiting, Joi Validation |
| **Real‑Time**     | Socket.IO |
| **Tools**         | Git, GitHub, Postman, Nodemon |

---

## Project Structure

```
Raritone-Project-Backend/
│
├── config/
│   ├── cloudinary.js
│   └── db.js
│
├── controllers/
│   ├── authController.js
│   ├── avatarController.js
│   ├── cartController.js
│   ├── googleAuthController.js
│   ├── imageController.js
│   ├── measurementController.js
│   ├── orderController.js
│   ├── productController.js
│   ├── profileController.js
│   ├── tryOnController.js
│   ├── wardrobeController.js
│   └── wishlistController.js
│
├── middleware/
│   ├── authMiddleware.js
│   ├── errorMiddleware.js
│   ├── roleMiddleware.js
│   ├── uploadMiddleware.js
│   └── validate.js
│
├── models/
│   ├── Avatar.js
│   ├── cart.js
│   ├── Image.js
│   ├── measurement.js
│   ├── order.js
│   ├── product.js
│   ├── ProductMapping.js
│   ├── Profile.js
│   ├── TryOn.js
│   ├── user.js
│   ├── Wardrobe.js
│   └── Wishlist.js
│
├── routes/
│   ├── authRoutes.js
│   ├── avatarRoutes.js
│   ├── cartRoutes.js
│   ├── imageRoutes.js
│   ├── measurementRoutes.js
│   ├── orderRoutes.js
│   ├── productRoutes.js
│   ├── profileRoutes.js
│   ├── tryOnRoutes.js
│   ├── wardrobeRoutes.js
│   └── wishlistRoutes.js
│
├── validators/
│   ├── authValidator.js
│   ├── avatarValidator.js
│   ├── loginValidator.js
│   ├── productValidator.js
│   ├── registerValidator.js
│   └── tryOnValidator.js
│
├── utils/
│   ├── cloudinaryUpload.js
│   └── generateToken.js
│
├── uploads/
├── app.js
├── server.js
├── package.json
└── README.md
```

---

## Modules Implemented

### Authentication Module
- User Registration & Login
- JWT Access (15 min) & Refresh (7 days) Tokens
- Google OAuth 2.0
- Role‑Based Access Control (USER, ADMIN, SUPER_ADMIN)
- Password Reset via Nodemailer

### Product Module
- Full CRUD operations (Admin only for write)
- Image upload pipeline: Multer → Sharp (800px, 80% quality) → Cloudinary
- Search & filter by keyword, category, price range
- Automatic Cloudinary cleanup on update/delete

### Wishlist Module
- Add/remove products with duplicate prevention
- Retrieve wishlist with populated product details

### Wardrobe Module
- Add clothing items (name, category, color, brand, image)
- View and delete wardrobe items

### Profile Module
- View/update profile bio and preferences (theme, language, notifications)
- Upload/delete profile and avatar images

### Cart Module
- Add to cart (creates cart if not exists)
- Update quantity (increment if product already in cart)
- Remove from cart, get cart with populated products

### Order Module
- Create order with shipping address
- Order status workflow: PENDING → PLACED → SHIPPED → DELIVERED / CANCELLED
- Retrieve all user orders or single order

### Measurement Module
- Save/update body measurements (chest, waist, shoulder, hip, height)
- Retrieve and delete measurements

### Avatar Module (Partial – routes ready, controller planned)
- Create, get, delete user avatars (future AI integration)

### Virtual Try‑On Module
- Upload original + generated try‑on images
- Store history, delete records
- Mock AI endpoints for future VITON‑HD/HR‑VITON integration

### Image Module
- Generic CRUD for images (profile, avatar, product, try‑on, fashion)
- Automatic Cloudinary cleanup on delete/update

### Product Mapping Module
- Stores relationships for AI recommendations: supportedBodyTypes, compatibility, avatarCompatibility

---

## Security Features

- **JWT Authentication** – Short‑lived access tokens + refresh tokens
- **Google OAuth** – Social login with `google-auth-library`
- **Helmet** – Secure HTTP headers (CSP, XSS protection)
- **Rate Limiting** – 100 requests per 15 minutes per IP
- **Role‑Based Access Control** – USER, ADMIN, SUPER_ADMIN
- **Input Validation** – Joi schemas for all request bodies
- **Centralized Error Handler** – Catches CastError, duplicate keys, JWT errors, etc.

---

## Database Relationships

- **User** → Profile (one‑to‑one), Wishlist, Cart, Orders, Measurements, Avatar, TryOn (one‑to‑many)
- **Cart / Order / Wishlist** → Product (many‑to‑one, populated via Mongoose)
- **ProductMapping** → Product (many‑to‑one, AI metadata)

---

## Testing

- **Tool:** Postman + MongoDB Compass
- **Tests performed:** CRUD operations, authentication, validation, protected routes, error handling, rate limiting
- **Result:** All major modules passed; wishlist auth missing (identified & to be fixed)

---

## Final Internship Deliverables

- ✅ Presentation (PPT)
- ✅ Technical Documentation
- ✅ Project Summary Report
- ✅ Key Learnings Report
- ✅ Challenges & Solutions Report
- ✅ Suggestions for Raritone Report
- ✅ Updated GitHub Repository
- ✅ README Documentation

---

## Team Contributions

| Member | Contributions |
|--------|---------------|
| **Nandini Bhimineni** | Team lead, integration, cart, order, measurement, avatar, product mapping, database design, cloud research, scalability, documentation |
| **Vagdevi Malineni** | Authentication, JWT, RBAC, profile module, wardrobe module |
| **Bharath Kumar** | Wishlist module, API validation, security enhancements, testing, avatar support |
| **Vishnu Vardhan Reddy** | Wishlist module, virtual try‑on support, authentication support, testing |
| **Meka Hrishi Teja Chowdary** | Product module, product APIs, order module, virtual try‑on workflows |
| **Nainisha Bandari** | Profile module, wardrobe module, user preferences |

---

## Future Enhancements

- **AI Avatar Generation** – Convert user photos into 3D avatars
- **AI Virtual Try‑On** – Replace mock endpoints with VITON‑HD / HR‑VITON
- **Recommendation Engine** – Use ProductMapping + user measurements
- **Redis Caching** – Cache product catalog and sessions
- **Docker & Kubernetes** – Containerized deployment and orchestration
- **AWS Deployment** – EC2, S3, CloudFront, ElastiCache
- **Real‑Time Notifications** – Socket.IO for order and try‑on updates

---

## Conclusion

The Raritone Backend System successfully provides a **secure, scalable, and modular backend foundation** for a virtual fashion platform while preparing the system for future AI‑powered features, advanced personalization, and cloud scalability.

---

*Developed during Summer Internship 2026 at Raritone Private Limited.*
```

---
