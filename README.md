# 🏝️ Resortify

A dynamic platform to discover, book, and explore luxurious resorts, offering users a seamless experience for planning memorable vacations.

## 🚀 Project Overview

**Resortify** is designed to simplify the process of finding and booking high-quality resorts tailored to user preferences. The platform combines detailed resort listings, advanced filtering options, and user reviews to ensure every user finds their perfect getaway.

### Key Features

- **Resort Listings**: Explore detailed listings with images, descriptions, and pricing information.
- **User Authentication**: Secure Login and Signup for user accounts.
- **Advanced Search**: Filter resorts based on location, price range, amenities, and ratings.
- **Image Uploads**: Resort owners can upload high-quality images to showcase their properties.
- **Review and Ratings**: Guests can leave reviews and rate their experiences at each resort.
- **Map Integration**: Visualize resort locations to find options nearby or in desired destinations.
- **Wishlist**: Save favorite resorts for future reference.

---

## 💻 Tech Stack

- **Frontend**: HTML, CSS, JavaScript, Tailwind CSS
- **Backend**: Node.js, Express.js
- **Database**: MongoDB
- **Additional Tools**: 
  - **Mapbox SDK** for location mapping
  - **Cloudinary** for image storage
  - **Passport.js** for user authentication

---

## 📁 Project Structure

### Models

#### Resort Model

```javascript
const resortSchema = new mongoose.Schema({
  name: { type: String, required: true },
  location: { type: String, required: true },
  pricePerNight: { type: Number, required: true },
  amenities: [String],
  images: [
    {
      filename: String,
      url: String,
    },
  ],
  reviews: [{ type: Schema.Types.ObjectId, ref: "Review" }],
  owner: { type: Schema.Types.ObjectId, ref: "User" },
  coordinates: {
    type: { type: String, enum: ["Point"], required: true },
    coordinates: { type: [Number], required: true },
  },
});
