import React from "react"; import { ShoppingCart, Search, Globe, ChevronRight, Truck, ShieldCheck, Headphones, CreditCard, Instagram, Facebook, Mail } from "lucide-react"; import { Card, CardContent } from "@/components/ui/card"; import { Button } from "@/components/ui/button";

// Minimal placeholder data const products = [ { id: 1, name: "Air Max Plus (Black/White)", price: "259,900₮", tag: "Sneakers" }, { id: 2, name: "Nike P-6000 (Silver)", price: "289,900₮", tag: "Sneakers" }, { id: 3, name: "Gym Tee — Oversize", price: "89,900₮", tag: "Clothing" }, { id: 4, name: "Tech Fleece Joggers", price: "149,900₮", tag: "Clothing" }, { id: 5, name: "Sabrina 2 (Court)", price: "319,900₮", tag: "Sneakers" }, { id: 6, name: "YoungLA Seamless Top", price: "119,900₮", tag: "Clothing" }, ];

const categories = [ { title: "Sneakers", subtitle: "Air Max, P-6000, Court" }, { title: "Clothing", subtitle: "Tee, Hoodie, Joggers" }, ];

export default function MonanStoreDemo() { return ( <div className="min-h-screen bg-white text-gray-900 antialiased"> {/* Top Bar */} <header className="sticky top-0 z-40 bg-white/80 backdrop-blur border-b"> <div className="max-w-6xl mx-auto flex items-center gap-3 px-4 py-3"> <div className="flex items-center gap-2"> <span className="text-2xl font-bold tracking-tight">Monan</span> <span className="text-2xl font-light tracking-tight">Store</span> </div>

<nav className="hidden md:flex ml-8 gap-6 text-sm">
        <a className="hover:opacity-70" href="#shop">Shop</a>
        <a className="hover:opacity-70" href="#sneakers">Sneakers</a>
        <a className="hover:opacity-70" href="#clothing">Clothing</a>
        <a className="hover:opacity-70" href="#sale">Sale</a>
        <a className="hover:opacity-70" href="#contact">Contact</a>
      </nav>

      <div className="ml-auto flex items-center gap-2 w-full md:w-auto">
        <div className="hidden md:flex relative items-center w-64">
          <Search className="absolute left-3 h-4 w-4 opacity-50" />
          <input
            placeholder="Хайх: Air Max, P-6000, Hoodie…"
            className="w-full pl-9 pr-3 py-2 rounded-xl border focus:outline-none focus:ring-2"
          />
        </div>

        <Button className="rounded-xl" variant="secondary">
          <Globe className="h-4 w-4 mr-2" /> MN / EN
        </Button>
        <Button className="rounded-xl" variant="default">
          <ShoppingCart className="h-4 w-4 mr-2" /> Cart (0)
        </Button>
      </div>
    </div>
  </header>

  {/* Hero */}
  <section className="border-b">
    <div className="max-w-6xl mx-auto grid md:grid-cols-2 gap-8 px-4 py-12 md:py-16">
      <div className="flex flex-col justify-center">
        <h1 className="text-4xl md:text-5xl font-semibold leading-tight">
          Minimal. Clean. Fast.
        </h1>
        <p className="mt-4 text-gray-600">
          Sneakers & Clothing — захиалга 4–11 хоног. Улаанбаатар + Орон нутаг хүргэлт.
          QPay / SocialPay / Хаан банк шилжихээр төлбөр төлнө.
        </p>
        <div className="mt-6 flex gap-3">
          <Button className="rounded-2xl px-5 py-6 text-base">Shop New Arrivals</Button>
          <Button className="rounded-2xl px-5 py-6 text-base" variant="secondary">
            View Sneakers <ChevronRight className="h-4 w-4 ml-1" />
          </Button>
        </div>
        <div className="mt-6 text-xs text-gray-500">
          * Demo layout — таны лого, зураг, өнгө, текстээр 100% өөрчилнө.
        </div>
      </div>

      <div className="bg-gray-50 border rounded-3xl h-72 md:h-96 flex items-center justify-center">
        <div className="text-center">
          <div className="mx-auto h-40 w-40 rounded-3xl border" />
          <p className="mt-4 text-sm text-gray-500">Hero Image Placeholder</p>
        </div>
      </div>
    </div>
  </section>

  {/* Categories */}
  <section id="shop" className="max-w-6xl mx-auto px-4 py-10">
    <div className="grid md:grid-cols-2 gap-4">
      {categories.map((c) => (
        <Card key={c.title} className="rounded-3xl border hover:shadow-sm transition">
          <CardContent className="p-6 md:p-8">
            <div className="flex items-center justify-between">
              <div>
                <h3 className="text-2xl font-semibold">{c.title}</h3>
                <p className="text-gray-500">{c.subtitle}</p>
              </div>
              <Button className="rounded-xl" variant="secondary">
                Explore <ChevronRight className="h-4 w-4 ml-1" />
              </Button>
            </div>
            <div className="mt-6 h-28 rounded-2xl bg-gray-50 border" />
          </CardContent>
        </Card>
      ))}
    </div>
  </section>

  {/* New Arrivals */}
  <section className="max-w-6xl mx-auto px-4 py-6">
    <div className="flex items-end justify-between mb-4">
      <h2 className="text-2xl font-semibold">New Arrivals</h2>
      <a href="#" className="text-sm text-gray-600 hover:underline">See all</a>
    </div>
    <div className="grid grid-cols-2 md:grid-cols-3 gap-4">
      {products.map((p) => (
        <Card key={p.id} className="rounded-3xl border hover:shadow-sm transition">
          <CardContent className="p-3">
            <div className="h-40 md:h-48 rounded-2xl bg-gray-50 border" />
            <div className="mt-3">
              <div className="flex items-center justify-between">
                <span className="text-xs text-gray-500">{p.tag}</span>
                <span className="text-xs">{p.price}</span>
              </div>
              <h3 className="mt-1 text-sm font-medium line-clamp-1">{p.name}</h3>
              <div className="mt-3 flex gap-2">
                <Button className="rounded-xl h-9 px-3 text-sm">Add to Cart</Button>
                <Button className="rounded-xl h-9 px-3 text-sm" variant="secondary">Details</Button>
              </div>
            </div>
          </CardContent>
        </Card>
      ))}
    </div>
  </section>

  {/* Service Highlights */}
  <section className="max-w-6xl mx-auto px-4 py-10">
    <div className="grid md:grid-cols-4 gap-3">
      <Card className="rounded-3xl"><CardContent className="p-6 flex items-start gap-3"><Truck className="h-5 w-5"/><div><div className="font-medium">4–11 хоног хүргэлт</div><div className="text-sm text-gray-500">УБ + Орон нутаг</div></div></CardContent></Card>
      <Card className="rounded-3xl"><CardContent className="p-6 flex items-start gap-3"><CreditCard className="h-5 w-5"/><div><div className="font-medium">QPay / SocialPay</div><div className="text-sm text-gray-500">Банк шилжих боломжтой</div></div></CardContent></Card>
      <Card className="rounded-3xl"><CardContent className="p-6 flex items-start gap-3"><ShieldCheck className="h-5 w-5"/><div><div className="font-medium">Баталгаат солилт</div><div className="text-sm text-gray-500">7 хоногийн дотор</div></div></CardContent></Card>
      <Card className="rounded-3xl"><CardContent className="p-6 flex items-start gap-3"><Headphones className="h-5 w-5"/><div><div className="font-medium">24/7 тусламж (бот)</div><div className="text-sm text-gray-500">Instagram / Web чат</div></div></CardContent></Card>
    </div>
  </section>

  {/* Footer */}
  <footer id="contact" className="border-t">
    <div className="max-w-6xl mx-auto px-4 py-10 grid md:grid-cols-4 gap-8">
      <div>
        <div className="text-xl font-semibold">Monan Store</div>
        <p className="mt-3 text-sm text-gray-600">Sneakers & Clothing — Minimal white store.</p>
        <div className="mt-4 flex gap-3">
          <a aria-label="Instagram" href="#" className="p-2 rounded-xl border hover:bg-gray-50"><Instagram className="h-4 w-4"/></a>
          <a aria-label="Facebook" href="#" className="p-2 rounded-xl border hover:bg-gray-50"><Facebook className="h-4 w-4"/></a>
          <a aria-label="Email" href="mailto:hello@monan.store" className="p-2 rounded-xl border hover:bg-gray-50"><Mail className="h-4 w-4"/></a>
        </div>
      </div>
      <div>
        <div className="font-medium">Shop</div>
        <ul className="mt-3 space-y-2 text-sm text-gray-600">
          <li><a href="#sneakers" className="hover:underline">Sneakers</a></li>
          <li><a href="#clothing" className="hover:underline">Clothing</a></li>
          <li><a href="#sale" className="hover:underline">Sale</a></li>
        </ul>
      </div>
      <div>
        <div className="font-medium">Support</div>
        <ul className="mt-3 space-y-2 text-sm text-gray-600">
          <li>Shipping & Returns</li>
          <li>Payments</li>
          <li>Size Guide</li>
        </ul>
      </div>
      <div>
        <div className="font-medium">Payments</div>
        <ul className="mt-3 space-y-2 text-sm text-gray-600">
          <li>QPay / SocialPay</li>
          <li>Хаан / Голомт шилжих</li>
          <li>COD (УБ) — сонголтоор</li>
        </ul>
      </div>
    </div>
    <div className="py-6 text-center text-xs text-gray-500">© {new Date().getFullYear()} Monan Store — All rights reserved.</div>
  </footer>
</div>

); }

