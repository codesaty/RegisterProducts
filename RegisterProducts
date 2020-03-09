class Product {
    constructor(ıd, Name, Cat, Stock, Cost, Price) {
        this.ıd = ıd;
        this.Name = Name;
        this.Cat = Cat;
        this.Stock = Stock;
        this.Cost = Cost;
        this.Price = Price;
    }
}

class PDC {
    addProduct(events) {
        const list = document.getElementById('Product-list');
        var web = `
        <tr>
        <td>${events.ıd}</td>
        <td>${events.Name}</td>
        <td>${events.Cat}</td>
        <td>${events.Stock}</td>
        <td>${events.Cost}₺</td>
        <td>${events.Price}₺</td>
       
        <td><a href="#" class="btn btn-danger btn-sm delete">Sil</a></td>
        </tr>
        `;
        list.innerHTML += web;
    }
    clearText() {
        const Id = document.getElementById('ıd').value = "";
        const name = document.getElementById('Name').value = "";
        const cat = document.getElementById('Cat').value = "";
        const Cost = document.getElementById('Cost').value = "";
        const stock = document.getElementById('Stock').value = "";
        const price = document.getElementById('Price').value = "";

    }
    deleteProduct(element) {
        if (element.classList.contains('delete')) {
            element.parentElement.parentElement.remove();
        }
    }
    alertMessage(message, classİtem) {
        var alert = `
        <div class="alert alert-${classİtem}">
        ${message}
         </div>
         `;
        const item = document.querySelector('.row');
        item.insertAdjacentHTML('beforeBegin', alert);
        setTimeout(() => {
            document.querySelector('.alert').remove();
        }, 3000)
    }
}
document.getElementById('new-products').addEventListener('submit', function (e) {
    const ıd = document.getElementById('ıd').value;
    const Name = document.getElementById('Name').value;
    const Cat = document.getElementById('Cat').value;
    const Stock = document.getElementById('Stock').value;
    const Cost = document.getElementById("Cost").value;
    const Price = document.getElementById('Price').value;

    const events = new Product(ıd, Name, Cat, Stock, Cost, Price);

    const pdc = new PDC();
    if (ıd === '' || Name === '' || Cat === '' || Cost === '' || Stock === '' || Price === '') {

        pdc.alertMessage('Boş Geçilemez', 'warning');

    } else {
        pdc.addProduct(events);
        pdc.clearText();
        pdc.alertMessage('Başarıyla Kaydedildi', 'success');
    }
    e.preventDefault();
});
document.getElementById('Product-list').addEventListener('click', function (e) {
    if (this.click === null) {
        pdc.alertMessage('Başarıyla Silindi', 'success');
    } else {
        const pdc = new PDC();
        pdc.deleteProduct(e.target);
    }
});
