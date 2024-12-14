index.html

<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Counter Project</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.3/css/all.min.css" integrity="sha512-iBBXm8fW90+nuLcSKlbmrPcLa0OT92xO1BIsZ+ywDWZCvqsWgccV3gFoRBv0z+8dLJgyAHIhR35VZc2oM/gI1w==" crossorigin="anonymous" />
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.0-beta3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-eOJMYsd53ii+scO/bJGFsiCZc+5NDVN2yr8+0RDqr0Ql0h+rP48ckxlpbzKgwra6" crossorigin="anonymous">
    <link rel="stylesheet" href="styles.css" />
  </head>
  <body>
    <main>
      <div>
        <h1>Counter</h1>
        <span class="value">0</span>
        <div>
          <button class="btn btn-danger decrease"><i class="fa fa-minus" aria-hidden="true"></i></button>
          <button class="btn btn-secondary reset">Reset</button>
          <button class="btn btn-success increase"><i class="fa fa-plus" aria-hidden="true"></i>
          </button>
        </div>
      </div>
    </main>
    <script src="index.js"></script>
  </body>
</html>

style.css

body {
  margin: 0;
  padding: 0;
  font-family: sans-serif;
  text-align: center;
}

h1 {
  font-size: 4rem;
}

.value {
  font-size: 6rem;
}

index.jss

let num = 0;

const value = document.querySelector(".value");
const btns = document.querySelectorAll(".btn");

btns.forEach((btn) => {
  btn.addEventListener("click", (e) => {
    const styles = e.currentTarget.classList;
    if (styles.contains("decrease")) {
      num--;
    } else if (styles.contains("increase")) {
      num++;
    } else {
      num = 0;
    }
    value.textContent = num;
    if (num > 0) {
      value.style.color = "green";
    } else if (num < 0) {
      value.style.color = "red";
    } else {
      value.style.color = "black";
    }
  });
});
