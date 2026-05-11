# -is_basvuru_formu
Flutter ile iş başvuru formu
import 'package:flutter/material.dart';

void main() => runApp(MaterialApp(debugShowCheckedModeBanner: false, home: BasvuruFormu()));

class BasvuruFormu extends StatefulWidget {
  @override
  _BasvuruFormuState createState() => _BasvuruFormuState();
}

class _BasvuruFormuState extends State<BasvuruFormu> {
  String dosyaYolu = "CV Dosyası Seçiniz"; // Dosya isminin duracağı yer

  Widget kutu(String yazi) {
    return Padding(
      padding: EdgeInsets.all(5),
      child: TextField(
        decoration: InputDecoration(
          filled: true,
          fillColor: Colors.white,
          labelText: yazi,
          labelStyle: TextStyle(color: Colors.black),
          border: OutlineInputBorder(borderSide: BorderSide.none),
        ),
      ),
    );
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      backgroundColor: Colors.pink,
      appBar: AppBar(backgroundColor: Colors.pink, title: Text("İş Başvurusu")),
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
              
              // CV Dosya Seçme Alanı
              GestureDetector(
                onTap: () => setState(() => dosyaYolu = "CV_Dosyasi_Eklendi.pdf"),
                child: Container(
                  margin: EdgeInsets.all(5),
                  padding: EdgeInsets.all(15),
                  decoration: BoxDecoration(color: Colors.white, borderRadius: BorderRadius.circular(4)),
                  child: Row(
                    mainAxisAlignment: MainAxisAlignment.spaceBetween,
                    children: [
                      Text(dosyaYolu, style: TextStyle(color: Colors.grey[700])),
                      Icon(Icons.file_upload, color: Colors.pink),
                    ],
                  ),
                ),
              ),

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


