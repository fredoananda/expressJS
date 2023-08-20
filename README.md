# expressJS
Ini adalah proyek contoh yang menggunakan Express.js untuk membuat aplikasi web sederhana.

## Instalasi

1. Clone repositori ini ke dalam direktori lokal Anda.
2. Buka terminal dan masuk ke direktori proyek.
3. Jalankan perintah berikut untuk menginstal semua dependensi:


## Menjalankan Aplikasi

1. Setelah instalasi selesai, jalankan aplikasi dengan perintah:


Aplikasi akan berjalan di http://localhost:3000.

<div>
  <pre>
    <code class="language-javascript">
      var express = require('express');
      var router = express.Router();

      /* GET home page. */
      router.get('/', function(req, res, next) {
        res.render('index', { title: 'Express' });
      });

      module.exports = router;
  </code>
  </pre>

</div>

untuk tampilan users

<div>
  <pre>
    <code class="language-javascript">
      var express = require('express');
      var router = express.Router();

      /* GET users listing. */
      router.get('/', function(req, res, next) {
      res.send('respond with a resource');
    });

    module.exports = router;

  </code>
  </pre>

</div>

## Struktur Proyek

app.js
<div>
  <pre>
    <code class="language-javascript">
      var createError = require('http-errors');
      var express = require('express');
      var path = require('path');
      var cookieParser = require('cookie-parser');
      var logger = require('morgan');

      var indexRouter = require('./routes/index');
      var usersRouter = require('./routes/users');

      var app = express();

      // view engine setup
      app.set('views', path.join(__dirname, 'views'));
      app.set('view engine', 'jade');

      app.use(logger('dev'));
      app.use(express.json());
      app.use(express.urlencoded({ extended: false }));
      app.use(cookieParser());
      app.use(express.static(path.join(__dirname, 'public')));

      app.use('/', indexRouter);
      app.use('/users', usersRouter);
      
      // catch 404 and forward to error handler
      app.use(function(req, res, next) {
        next(createError(404));
      });
      
      // error handler
      app.use(function(err, req, res, next) {
        // set locals, only providing error in development
        res.locals.message = err.message;
        res.locals.error = req.app.get('env') === 'development' ? err : {};
      
        // render the error page
        res.status(err.status || 500);
        res.render('error');
      });
      
      module.exports = app;


  </code>
  </pre>
 
</div>

- `routes/`: Direktori yang berisi definisi rute aplikasi.
- `views/`: Direktori yang berisi template tampilan menggunakan engine `jade`.
- `public/`: Direktori untuk file statis seperti gambar dan stylesheet.
- `app.js`: Berkas utama aplikasi.

## Kontribusi

Jika Anda ingin berkontribusi pada proyek ini, silakan buat _fork_ dari repositori ini, lakukan perubahan yang diperlukan, dan ajukan _pull request_.

## Masalah

Jika Anda menemukan masalah atau memiliki pertanyaan, silakan buat _issue_ di repositori ini.

---

**Catatan:** Proyek ini dibuat untuk tujuan demonstrasi. Anda bebas menggunakan, mengubah, atau mendistribusikan kode ini sesuai dengan kebutuhan Anda.
