# Bulk Vegetable/Fruit Ordering Platform

A simple web application for bulk ordering vegetables and fruits. Buyers can browse products, place orders, and track their order status. Admins can view all orders and update their delivery status.

## 🚀 Features

### For Buyers
- **Browse Products**: View a catalogue of available vegetables and fruits with prices
- **Place Orders**: Order products by providing:
  - Product name
  - Quantity
  - Buyer name
  - Delivery address
- **Order Tracking**: Check order status using Order ID
  - Order status: Pending or Delivered

### For Admin
- **View All Orders**: See a complete list of all placed orders
- **Update Order Status**: Change order status from Pending to Delivered

## 🛠️ Tech Stack

### Backend
- **Node.js** with Express.js
- **SQLite** database (local file-based)
- RESTful API architecture

### Frontend
- **React.js** (Create React App)
- **React Router** for navigation
- **Axios** for API calls

### Database
- **SQLite** with two main tables:
  - `products`: Stores product information (name, price per unit)
  - `orders`: Stores order details (order_id, buyer info, product, quantity, address, status)

## 📁 Project Structure

```
.
├── backend/
│   ├── server.js          # Express server and API routes
│   ├── package.json       # Backend dependencies
│   └── database.sqlite    # SQLite database (created on first run)
├── frontend/
│   ├── public/
│   ├── src/
│   │   ├── components/    # React components
│   │   │   ├── ProductCatalogue.js
│   │   │   ├── OrderForm.js
│   │   │   ├── OrderTracking.js
│   │   │   └── AdminOrders.js
│   │   ├── services/
│   │   │   └── api.js    # API service functions
│   │   ├── App.js        # Main app component with routing
│   │   └── index.js      # React entry point
│   └── package.json      # Frontend dependencies
└── README.md
```

## 🚀 Steps to Run Locally

### Prerequisites
- Node.js (v14 or higher)
- npm (comes with Node.js)

### Backend Setup

1. Navigate to the backend directory:
```bash
cd backend
```

2. Install dependencies:
```bash
npm install
```

3. Start the server:
```bash
npm start
```

For development with auto-reload:
```bash
npm run dev
```

The backend server will run on `http://localhost:5000`

The SQLite database (`database.sqlite`) will be automatically created in the backend directory on first run, along with sample products.

### Frontend Setup

1. Open a new terminal and navigate to the frontend directory:
```bash
cd frontend
```

2. Install dependencies:
```bash
npm install
```

3. Start the development server:
```bash
npm start
```

The frontend will run on `http://localhost:3000` and automatically open in your browser.

### Environment Variables (Optional)

If your backend is running on a different port or URL, create a `.env` file in the frontend directory:

```
REACT_APP_API_URL=http://localhost:5000/api
```

## 📡 API Endpoints

### Products
- `GET /api/products` - Get all products

### Orders
- `POST /api/orders` - Place a new order
  - Body: `{ product_name, quantity, buyer_name, delivery_address }`
- `GET /api/orders/:orderId` - Get order status by Order ID

### Admin
- `GET /api/admin/orders` - Get all orders
- `PUT /api/admin/orders/:orderId` - Update order status
  - Body: `{ status: "Pending" | "Delivered" }`

## 🗄️ Database Schema

### Products Table
```sql
CREATE TABLE products (
  id INTEGER PRIMARY KEY AUTOINCREMENT,
  name TEXT NOT NULL,
  price_per_unit REAL NOT NULL,
  created_at DATETIME DEFAULT CURRENT_TIMESTAMP
);
```

### Orders Table
```sql
CREATE TABLE orders (
  id INTEGER PRIMARY KEY AUTOINCREMENT,
  order_id TEXT UNIQUE NOT NULL,
  buyer_name TEXT NOT NULL,
  product_name TEXT NOT NULL,
  quantity INTEGER NOT NULL,
  delivery_address TEXT NOT NULL,
  status TEXT DEFAULT 'Pending',
  created_at DATETIME DEFAULT CURRENT_TIMESTAMP
);
```

## 🎯 Usage Guide

### For Buyers

1. **Browse Products**: Visit the home page to see all available products
2. **Place Order**: 
   - Click "Place Order" in the navigation
   - Fill in the form with product, quantity, your name, and delivery address
   - Submit the form
   - **Save the Order ID** that appears after successful submission
3. **Track Order**: 
   - Click "Track Order" in the navigation
   - Enter your Order ID
   - View order details and status

### For Admin

1. **View Orders**: Click "Admin" in the navigation to see all orders
2. **Update Status**: Click "Mark as Delivered" button next to pending orders

## 🚢 Deployment

### Frontend (Vercel/Netlify)

1. Build the React app:
```bash
cd frontend
npm run build
```

2. Deploy the `build` folder to Vercel or Netlify

3. Set environment variable:
   - `REACT_APP_API_URL` = Your backend API URL

### Backend (Render)

1. Push your code to GitHub
2. Connect your repository to Render
3. Set build command: `npm install`
4. Set start command: `npm start`
5. Set environment variables if needed

**Note**: For Render deployment, you may need to use a persistent database solution or configure SQLite to use a persistent volume.

## 📸 Screenshots

### Product Catalogue
- Displays all available vegetables and fruits in a grid layout
- Shows product name and price per unit

### Order Form
- Clean form with dropdown for product selection
- Input fields for quantity, buyer name, and delivery address
- Success message with Order ID after submission

### Order Tracking
- Simple search interface to enter Order ID
- Displays complete order details with status badge

### Admin Panel
- Table view of all orders
- Action buttons to update order status
- Status badges for visual clarity

## ✅ Features Implemented

- ✅ Product catalogue display
- ✅ Order placement with validation
- ✅ Order tracking by Order ID
- ✅ Admin order management
- ✅ Order status update (Pending → Delivered)
- ✅ SQLite database with Products and Orders tables
- ✅ RESTful API with proper HTTP methods
- ✅ Responsive UI design
- ✅ Error handling and user feedback

## 🔧 Future Enhancements

- User authentication
- Order history for buyers
- Product images
- Order cancellation
- Email notifications
- Payment integration
- Inventory management

## 📝 License

This project is open source and available for educational purposes.

---

**Note**: This is a simple demonstration project. For production use, consider adding authentication, input sanitization, rate limiting, and more robust error handling.

