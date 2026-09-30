# Giridhari Silks & Jewels - Luxury Indian Ethnic Fashion E-Commerce Platform

A production-ready, full-stack women's luxury ethnic fashion shopping platform specializing in authentic pure silk sarees (Kanjivaram, Banarasi, Organza, Mysore Silk), BIS-hallmarked temple & polki kundan jewellery, bridal lehengas, and handcrafted ethnic accessories.

Built with **Next.js 16 (App Router)**, **TypeScript**, **Tailwind CSS v4**, **Lucide Icons**, and architected for **Supabase (PostgreSQL & Auth)** and **Razorpay** online payments.

---

## 🌟 Key Features

### 1. Storefront & Luxury Brand Identity
- **Royal Boutique Aesthetic:** Deep wine / burgundy tones (`#4B0922`), champagne gold accents (`#D4AF37`), warm ivory backgrounds (`#FDFBF7`), serif headlines (*Playfair Display*), clean sans-serif body (*Plus Jakarta Sans*).
- **Dynamic Announcement Bar:** Real-time offer ticker, free shipping threshold counter, VIP WhatsApp concierge link.
- **Header & Mega Menu:** Multi-level dropdowns for Sarees, Jewellery, Women's Clothing, Accessories, and Beauty & Wellness.
- **Interactive Search:** Live autocomplete search modal with instant thumbnails, price tags, and popular search tags.
- **Hero Showcase:** Dual-action hero banner, trust metrics, Silk Mark certification callout.
- **Curated Collections:** Trending Sarees, Royal Heritage Jewellery, Festive & Wedding Trousseau edit, Customer Testimonials, and Instagram-style social gallery.

### 2. Product Catalog & Details
- **Faceted Product Filters:** Real-time filtering by Category, Subcategory, Price Range slider, Fabric/Material, Occasion (Bridal, Reception, Festive, etc.), Stock availability, and Star rating.
- **Multi-angle Image Gallery:** Interactive zoom magnifier on hover, thumbnail switcher, Silk Mark badges.
- **Specifications & Purity:** Transparent breakdown of saree length, blouse piece dimensions, zari gilding type, metal purity (925 sterling silver / 24K gold polish), and care instructions.
- **Pincode Serviceability Check:** Live estimated delivery calculator for any 6-digit Indian PIN code.
- **Reviews & Ratings:** Customer review breakdowns and review submission modal.
- **Quick-View Modal:** Direct product preview modal from any product listing card.

### 3. Shopping Bag & Checkout
- **Persistent Cart:** Automatic localStorage persistence with server-side stock and price validation.
- **Free Shipping Progress Meter:** Dynamic threshold meter towards complimentary express delivery.
- **Privilege Coupon System:** Built-in validation supporting percentage discounts, flat cash discounts, caps, and minimum order values (e.g. `ROYAL10`, `FESTIVE500`, `BRIDAL15`).
- **4-Step Secure Checkout:**
  1. Patron Contact Information
  2. Delivery Destination Address
  3. Payment Mode (Razorpay or Cash on Delivery)
  4. Order Review & Confirmation
- **Instant Tax Invoice:** Printable GST-compliant tax receipt on the Order Confirmation page.

### 4. Customer Account & Order Tracking
- **Order Timeline:** Real-time visual tracking from *Order Confirmed* → *Artisan Quality Check* → *Dispatched with Courier (AWB tracking)* → *Delivered*.
- **Post-Purchase Operations:** Self-service order cancellation (with automatic inventory restoration) and 7-day doorstep return/exchange requests.
- **Address Book:** Manage default home and work delivery destinations.
- **Wishlist:** Quick heart toggle to save desired heirlooms.

### 5. Enterprise Admin Dashboard (`/admin`)
- **Executive Overview:** Gross revenue, total orders, average order value, pending fulfillments, low-stock inventory alerts, and sales distribution by category.
- **Product Management (`/admin/products`):** Full CRUD for adding, updating, and removing products with images, variants, stock, and SEO slugs.
- **Order Management (`/admin/orders`):** Order status management, courier partner selection, and Air Waybill (AWB) recording.
- **Coupon Management (`/admin/coupons`):** Create and toggle active promotional codes.
- **Clientele Registry (`/admin/customers`):** Lifetime spend tracking and patron order frequency.
- **Boutique Settings (`/admin/settings`):** Live configuration of free shipping limits, COD ceilings, store address, and GST percentages.

---

## 📁 Project Structure

```
giridhari-silks/
├── src/
│   ├── app/
│   │   ├── layout.tsx                     # Root layout with luxury typography & metadata
│   │   ├── globals.css                    # Tailwind v4 theme tokens & luxury utilities
│   │   ├── page.tsx                       # Homepage with all curated sections
│   │   ├── products/page.tsx              # Product catalog with sidebar & mobile filters
│   │   ├── product/[slug]/page.tsx        # High-res product details with zoom & pincode check
│   │   ├── category/[slug]/page.tsx       # Dynamic category redirect route
│   │   ├── cart/page.tsx                  # Dedicated shopping bag page
│   │   ├── checkout/page.tsx              # 4-step mobile-responsive checkout flow
│   │   ├── order-confirmation/[id]/       # Order celebration & printable tax invoice
│   │   ├── account/                       # Customer profile & saved addresses
│   │   │   └── orders/                    # Customer order list & timeline tracking
│   │   ├── wishlist/page.tsx              # Saved wishlist grid
│   │   ├── search/page.tsx                # Keyword search results page
│   │   ├── about/page.tsx                 # Brand legacy & master weavers
│   │   ├── contact/page.tsx               # Boutique locator & WhatsApp concierge
│   │   ├── shipping-policy/page.tsx       # Shipping policy & transit insurance
│   │   ├── return-policy/page.tsx         # 7-day return guarantee
│   │   ├── terms/page.tsx                 # Terms of service
│   │   ├── privacy/page.tsx               # Privacy & data protection
│   │   ├── not-found.tsx                  # Custom luxury 404 page
│   │   ├── sitemap.ts                     # Search engine XML sitemap generator
│   │   ├── robots.ts                      # Search engine robots.txt
│   │   ├── admin/                         # Admin ERP Dashboard
│   │   │   ├── layout.tsx                 # Admin sidebar & header
│   │   │   ├── page.tsx                   # Sales analytics & low-stock alerts
│   │   │   ├── products/page.tsx          # Product creation & stock editor
│   │   │   ├── orders/page.tsx            # Order fulfillment & courier tracking
│   │   │   ├── coupons/page.tsx           # Promotional coupon manager
│   │   │   ├── customers/page.tsx         # Customer registry & lifetime spend
│   │   │   └── settings/page.tsx          # Store settings & COD limits
│   │   └── api/                           # Backend Server Routes
│   │       └── checkout/
│   │           ├── create-order/route.ts  # Server price & stock validation, Razorpay order
│   │           └── verify-payment/route.ts# Cryptographic HMAC-SHA256 signature verification
│   ├── components/
│   │   ├── layout/                        # Header, AnnouncementBar, Navbar, Footer, MobileDrawer
│   │   ├── home/                          # HeroBanner, CategoryShowcase, Sarees, Jewellery, Tabs
│   │   ├── products/                      # ProductCard, ProductFilters, QuickViewModal
│   │   ├── cart/                          # CartDrawer, Free shipping meter
│   │   ├── navigation/                    # SearchModal with live suggestions
│   │   └── providers/                     # Providers wrapper for Auth, Cart, Wishlist
│   ├── context/
│   │   ├── AuthContext.tsx                # Customer auth & Admin mode switch
│   │   ├── CartContext.tsx                # Shopping bag state & coupon calculation
│   │   └── WishlistContext.tsx            # Saved items state
│   ├── data/
│   │   ├── categories.ts                  # Categories & subcategories hierarchy
│   │   ├── products.ts                    # Realistic luxury Indian ethnic product seed data
│   │   └── storeConfig.ts                 # Brand configuration, coupons, reviews
│   ├── lib/
│   │   ├── storeService.ts                # Central data provider & in-memory state sync
│   │   ├── modalEvents.ts                 # Lightweight global event bus
│   │   └── supabase/                      # Supabase client & server admin helpers
│   └── types/
│       └── index.ts                       # Complete TypeScript interface definitions
├── supabase/
│   ├── schema.sql                         # PostgreSQL schema with Row Level Security (RLS)
│   └── seed.sql                           # Initial categories and coupons database seed
├── .env.example                           # Configuration environment variables template
└── next.config.ts                         # Remote image domains configuration
```

---

## 🚀 Running Locally

1. **Clone or navigate to the repository:**
   ```bash
   cd "e:\Jeswin\Giridhari Silks"
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Start the local development server:**
   ```bash
   npm run dev
   ```

4. **Open in browser:**
   Navigate to [http://localhost:3000](http://localhost:3000)

---

## 🔑 Supabase Database & Auth Setup

1. Create a new project at [supabase.com](https://supabase.com).
2. Go to the **SQL Editor** tab in your Supabase project dashboard.
3. Open `supabase/schema.sql` from this repository, copy its contents, paste them into the SQL editor, and click **Run**. This establishes all 15 tables, constraints, foreign keys, and Row Level Security (RLS) policies.
4. Run `supabase/seed.sql` to populate default categories and coupons.
5. In your Supabase Project Settings > **API**, copy:
   - Project URL → `NEXT_PUBLIC_SUPABASE_URL`
   - Anon Public Key → `NEXT_PUBLIC_SUPABASE_ANON_KEY`
   - Service Role Key → `SUPABASE_SERVICE_ROLE_KEY`
6. Create a `.env.local` file and paste the credentials.

---

## 💳 Razorpay Online Payments Setup

1. Sign up or log into [dashboard.razorpay.com](https://dashboard.razorpay.com).
2. Navigate to **Account & Settings > API Keys**.
3. Generate **Test API Keys** (`Key ID` and `Key Secret`).
4. Add them to your `.env.local`:
   ```env
   RAZORPAY_KEY_ID=rzp_test_...
   RAZORPAY_KEY_SECRET=...
   ```
5. In development, the platform automatically runs in test mode with instant verification. In production, provide live credentials to authorize UPI, Cards, and NetBanking.

---

## ☁️ Deployment on Vercel

1. Push your repository to GitHub / GitLab / Bitbucket.
2. Log into [vercel.com](https://vercel.com) and click **"Add New Project"**.
3. Select this repository.
4. Under **Environment Variables**, paste the variables from `.env.example`:
   - `NEXT_PUBLIC_SUPABASE_URL`
   - `NEXT_PUBLIC_SUPABASE_ANON_KEY`
   - `SUPABASE_SERVICE_ROLE_KEY`
   - `RAZORPAY_KEY_ID`
   - `RAZORPAY_KEY_SECRET`
   - `NEXT_PUBLIC_SITE_URL` (Set to your Vercel domain, e.g. `https://giridhari-silks.vercel.app`)
5. Click **Deploy**. Vercel will build the production bundle automatically.
