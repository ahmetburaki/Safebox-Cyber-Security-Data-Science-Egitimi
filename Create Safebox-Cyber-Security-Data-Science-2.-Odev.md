### İkinci Ödev

Bu kod, kullanıcıdan bir sayı girerek bir film seçmesini sağlar ve seçilen film adını bir txt dosyasına kaydeder.

İşleyişi şu şekildedir:

- "MovieSelector" adlı bir sınıf tanımlanır. Bu sınıf, film listesini ve dosya adını alır.
-  "__init__" metodu, sınıfın başlatılmasında çalışır ve film listesini ve dosya adını ilgili özelliklere atar.
- "select_movie" metodu, kullanıcının girdiği sayıya göre film listesinden bir film seçer ve seçilen film adını döndürür.
- "save_to_txt" metodu, verilen film adını txt dosyasına kaydeder.
- "movie_list" değişkeni, mevcut filmleri içeren bir liste olarak tanımlanır.
- "file_name" değişkeni, film adının kaydedileceği txt dosyasının adını belirtir.
- "MovieSelector" sınıfından bir nesne oluşturulur, film listesi ve dosya adı ile başlatılır.
- Kullanıcıdan bir sayı girmesi istenir ve seçilen film adı "selected_movie" değişkenine atanır.
- Seçilen film adı ekrana yazdırılır.
- "save_to_txt" metodu çağrılarak seçilen film adı txt dosyasına kaydedilir.
- "Movie saved to TXT file." mesajı ekrana yazdırılır.

Bu kod, basit bir film seçici uygulamasıdır. Kullanıcıya 1-5 arasında bir sayı seçmesi istenir ve seçilen film adı "selected_movie.txt" adlı bir txt dosyasına kaydedilir.

```python
class MovieSelector:
    def __init__(self, movie_list, file_name):
        self.movie_list = movie_list
        self.file_name = file_name

    def select_movie(self, number):
        selected_movie = self.movie_list[int(number)-1]
        return selected_movie

    def save_to_txt(self, movie_name):
        with open(self.file_name, "w") as file:
            file.write(movie_name)

movie_list = ["Movie 1", "Movie 2", "Movie 3", "Movie 4", "Movie 5"]
file_name = "selected_movie.txt"

movie_selector = MovieSelector(movie_list, file_name)

a = input("Select a movie 1-5: ")
selected_movie = movie_selector.select_movie(a)
print("Selected movie: " + selected_movie)

movie_selector.save_to_txt(selected_movie)
print("Movie saved to TXT file.")
```
