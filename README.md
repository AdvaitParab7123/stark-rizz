# The Cold Approach Protocol — Sales Funnel & Access System

An ultra-minimalist, high-converting, single-page sales funnel and post-payment access system built with single-file HTML5 and Tailwind CSS.

## ?? Live Pages
- **Sales Funnel (`index.html`)**: Distraction-free, mobile-first sales page with an animated high-contrast CTA button wired to Razorpay.
- **Access & Download Page (`access.html`)**: Instant post-payment delivery page with direct PDF download and browser preview fallback.

## ?? Razorpay Payment Pages Setup

1. Log in to [Razorpay Dashboard](https://dashboard.razorpay.com).
2. Navigate to **Payment Pages** ? click **Create Payment Page**.
3. Set your title (e.g. *The Cold Approach Protocol*), price (`?499`), and require Customer Name + Email.
4. Go to **Page Settings** (gear icon) ? **Action after payment** ? select **Redirect to your website**.
5. Set the redirect URL to your deployed access page:
   - `https://your-domain.com/access.html`
6. Copy your Razorpay link (e.g. `https://rzp.io/l/your-link`) and update `RAZORPAY_PAYMENT_PAGE_URL` in `index.html`:
   ```javascript
   const RAZORPAY_PAYMENT_PAGE_URL = 'https://rzp.io/l/your-link';
   ```

## ?? PDF Delivery Setup

- Place your final PDF ebook in the `guides/` folder (e.g., `guides/the-cold-approach-protocol.pdf`).
- In `access.html`, update the file path:
   ```javascript
   const PDF_DOWNLOAD_URL = './guides/the-cold-approach-protocol.pdf';
   const PDF_FILENAME = 'The-Cold-Approach-Protocol.pdf';
   ```
*(You can also use an external AWS S3, Google Drive, or Cloudflare R2 link).*

## ?? Deployment
- **Vercel / Netlify**: Simply import this GitHub repository. Zero build commands needed (`Framework: Other`).
- **GitHub Pages**: In repo Settings ? Pages ? select `Deploy from a branch` ? `main` / `root`.
