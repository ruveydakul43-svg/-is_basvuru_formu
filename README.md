# -is_basvuru_formu
Flutter ile iş başvuru formu
import 'package:flutter/material.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      debugShowCheckedModeBanner: false,
      home: BasvuruFormu(),
    );
  }
}

class BasvuruFormu extends StatelessWidget {

  Widget kutu(String yazi) {
    return Padding(
      padding: EdgeInsets.all(5),

      child: TextField(
        style: TextStyle(
          color: Colors.black,
        ),

        decoration: InputDecoration(
          filled: true,
          fillColor: Colors.white, // Kutular beyaz

          labelText: yazi,

          labelStyle: TextStyle(
            color: Colors.black,
          ),

          enabledBorder: OutlineInputBorder(
            borderSide: BorderSide(color: Colors.white),
          ),

          focusedBorder: OutlineInputBorder(
            borderSide: BorderSide(color: Colors.black),
          ),
        ),
      ),
    );
  }

  @override
  Widget build(BuildContext context) {

    return Scaffold(

      backgroundColor: Colors.pink, // Arka plan pembe

      appBar: AppBar(
        backgroundColor: Colors.pink,

        title: Text(
          "İş Başvurusu",
          style: TextStyle(color: Colors.white),
        ),
      ),

      body: SingleChildScrollView(
        child: Padding(
          padding: EdgeInsets.all(15),

          child: Column(
            children: [

              kutu("İsim"),
              kutu("Soyisim"),
              kutu("Adres"),
              kutu("Email"),
              kutu("Telefon"),
              kutu("Pozisyon"),
              kutu("CV Linki Ekleyiniz"),

              SizedBox(height: 20),

              ElevatedButton(
                onPressed: () {},
                child: Text("Gönder"),
              )

            ],
          ),
        ),
      ),
    );
  }
}