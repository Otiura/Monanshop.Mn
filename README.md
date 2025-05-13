// Monan Shop Simple Order Website import React from 'react'; import { Card, CardContent } from "@/components/ui/card"; import { Button } from "@/components/ui/button"; import { Input } from "@/components/ui/input";

export default function MonanShop() { return ( <div className="p-4 max-w-4xl mx-auto"> <h1 className="text-3xl font-bold mb-6 text-center">Monan Shop – Захиалгаар</h1>

<div className="grid grid-cols-1 md:grid-cols-3 gap-4 mb-8">
    {[1, 2, 3].map((id) => (
      <Card key={id}>
        <CardContent className="p-4">
          <img
            src={`/products/shoe${id}.jpg`}
            alt={`Product ${id}`}
            className="rounded-xl mb-2"
          />
          <p className="font-semibold">Sneakers {id}</p>
          <p className="text-sm">Үнэ: 95,000₮ (9-14 хоногт ирнэ)</p>
        </CardContent>
      </Card>
    ))}
  </div>

  <h2 className="text-2xl font-semibold mb-4">Захиалга өгөх</h2>
  <form className="grid grid-cols-1 md:grid-cols-2 gap-4">
    <Input placeholder="Нэр" required />
    <Input placeholder="Утасны дугаар" required />
    <Input placeholder="Захиалах бараа (жишээ: Sneakers 1)" required />
    <Input placeholder="Хаяг / Хүргэлт" required />
    <Input placeholder="Instagram хаяг (жишээ: @monan_shop)" />
    <Input placeholder="Гүйлгээ хийсэн огноо" />
    <div className="md:col-span-2">
      <Button className="w-full">Захиалга илгээх</Button>
    </div>
  </form>

  <div className="mt-10">
    <h3 className="text-xl font-semibold">Төлбөрийн мэдээлэл</h3>
    <p>Хаан банк: 5679196551</p>
    <p>Төмөрбаатар Мөнгөнтулга</p>
    <p>Гүйлгээний утга: Захиалгын код (жишээ: MS20250513-01)</p>
  </div>
</div>

); }

