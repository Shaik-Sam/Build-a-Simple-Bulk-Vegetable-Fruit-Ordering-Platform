# Quick Setup Guide

## Prerequisites
- Node.js (v14 or higher) and npm installed

## Quick Start

### 1. Backend Setup (Terminal 1)
```bash
cd backend
npm install
npm start
```
Backend will run on http://localhost:5000

### 2. Frontend Setup (Terminal 2)
```bash
cd frontend
npm install
npm start
```
Frontend will open automatically at http://localhost:3000

## Testing the Application

1. **Browse Products**: Visit http://localhost:3000 - you should see 10 sample products
2. **Place an Order**: 
   - Click "Place Order"
   - Fill the form and submit
   - Copy the Order ID shown
3. **Track Order**: 
   - Click "Track Order"
   - Enter the Order ID
   - View order details
4. **Admin Panel**: 
   - Click "Admin"
   - View all orders
   - Click "Mark as Delivered" to update status

## Sample Products Included
- Tomatoes, Potatoes, Onions, Carrots, Cabbage
- Cauliflower, Spinach
- Apples, Bananas, Oranges

All products are automatically added to the database on first backend run.

## Troubleshooting

**Backend won't start:**
- Check if port 5000 is available
- Run `npm install` again in backend folder

**Frontend can't connect to backend:**
- Ensure backend is running on port 5000
- Check browser console for CORS errors
- Verify API URL in `frontend/src/services/api.js`

**Database issues:**
- Delete `backend/database.sqlite` and restart backend
- Database will be recreated with sample data

