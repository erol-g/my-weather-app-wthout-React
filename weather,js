// June 2022  //


 let now = new Date();
 let dateNow =    document.querySelector(".date");
 dateNow.innerText = now.toLocaleString();


const api = {
    key: "843795bbd1706de5dcdefe13c777f815",
    baseUrl: "https://api.openweathermap.org/data/2.5/"
    // https://api.openweathermap.org/data/2.5/weather?q=Istanbul&lang=tr&units=metric&appid=843795bbd1706de5dcdefe13c777f815  //  
}

const searchInput = document.querySelector(".search-box");

searchInput.addEventListener('keypress', callbackFunc);
 
function callbackFunc(event) {
    console.log("You clicked to enter")
    if (event.keyCode == 13)
    getResult(searchInput.value);    
}
 
function getResult(searchText) {
    fetch(`${api.baseUrl}weather?q=${searchText}&units=metric&appid=${api.key}`)
        .then(resp => resp.json())
        .then(weather => displayResult(weather))
        .catch((err) => {
            console.log(err);
            searchInput.value = `Try again with correct city name, please !`;
        });
    setTimeout(() => {
            searchInput.value = "";
    }, 3000);
}

function displayResult(weather) {
        let city = document.querySelector(".city");
        city.innerText = `${weather.name} ${weather.sys.country}`;

        let temperature = document.querySelector(".temperature");
        temperature.innerText = `${Math.round(weather.main.temp)} °C`;

        let now = new Date();
        let dateNow = document.querySelector(".date");
        dateNow.innerText = now.toLocaleString();
} 
