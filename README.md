DESKRIPSI CODE BASH DI DALAM FILE `sampling.sh`

1. `wget https://github.com/labusiam/dataset/raw/main/weather_data.xlsx` Download weather_data.xlsx
2. `in2csv weather_data.xlsx --sheet "weather_2014" > weather_2014.csv` Convert sheet weather_2014 menjadi weather_2014.csv
3. `in2csv weather_data.xlsx --sheet "weather_2015" > weather_2015.csv` Convert sheet weather_2015 menjadi weather_2015.csv
4. `csvstack weather_2014.csv weather_2015.csv > weather.csv` Menggabungkan weather_2014.csv dan weather_2015.csv menjadi 1 file csv
5. `rm weather_data.xlsx` Hapus file weather_data.xlsx
6. `csvlook weather.csv | sample -r 0.3 > sample_weather.csv` Sampling weather.csv dengan proporsi 0.3 dari total file dan simpan di file sample_weather.csv
