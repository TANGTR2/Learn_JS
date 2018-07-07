#1 格式化barcodes V
input:
    tags: [String]
output:
    formattedBarcodes: [{
        barcode: String,
        count: Number
    }]

#2 统计购买的商品数量 V
input:
    formattedBarcodes
output:
    cartItems: [{
        barcode: String,
        count: Number
    }]

#3 计算赠品 v
input:
    allItems: ... : loadAllItems()
    promotions: ... : loadPromotions()
    cartItems
output:
    gifts: [{
        barcode: String,
        count: Number,
        price: Number
    }]
    


#4 丰富小票项 V
input:
    allItems
    cartItems
output:
    receiptItems: [{
        barcode: String
        name: String,
        count: Number,
        unit: String,
        price: Numbner
    }]

#5 计算小票项的价格 v

input:
    receiptItems
    gifts
output:
    receiptItems: [{
        barcode: String
        name: String,
        count: Number,
        unit: String,
        price: Numbner,
        subTotal: Number
    }]

#6 计算total v
input:
    receiptItems
output:
    total: Number

#7 计算saved v
input:
    gifts
output:
    saved: Number

#8 生成viewModel
input:
    receiptItems
    total
    saved
output:
    viewModel: [
        receiptItems: [{
            name: String,
            count: Number,
            unit: String,
            price: Numbner,
            subTotal: Number    
        }],
        total: Number,
        saved: Number
    ]

#9 打印
input:
    viewModel
output:
    result: String
