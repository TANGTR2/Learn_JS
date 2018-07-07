#1 格式化barcodes
input:
    tags: [String]
output:
    cartItems: [{
        barcode: String,
        count: Number
    }]

#.....

#N-1 生成viewModel
input:
    ?
output:
    viewModel: [
        receiptItems: [{
            name: String,
            count: Number,
            unit: String,
            price: String,
            subTotal: String    
        }],
        total: String,
        saved: String
    ]

#N 打印
input:
    viewModel
output:
    result: String
