#1 格式化barcodes
input:
    tags: [String]
output:
    cartItems: [{
        barcode: String,
        count: Number
    }]  

#2 计算小票项
input:
    allItems
    promotions
    cartItems
output:
    receiptItems: [{
        barcode: String
        name: String,
        count: Number,
        unit: String,
        price: Numbner,
        subTotal: Number
    }]

#3 计算total
input:
    receiptItems
output:
    total: Number

#4 计算saved
input:
    receiptItems
output:
    saved: Number

#5 生成viewModel
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

#6 打印
input:
    viewModel
output:
    result: String
