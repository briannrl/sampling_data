DESKRIPSI CODE BASH DI DALAM FILE `sampling.sh`

1. `if [[ ! -d data ]]; then
        mkdir data
    fi`
    Membuat folder data jika belum ada
2. `wget -P data https://github.com/labusiam/dataset/raw/main/weather_data.xlsx` Download weather_data.xlsx di folder data
3. `in2csv data/weather_data.xlsx --sheet "weather_2014" > data/weather_2014.csv` Convert sheet weather_2014 menjadi weather_2014.csv
4. `in2csv data/weather_data.xlsx --sheet "weather_2015" > data/weather_2015.csv` Convert sheet weather_2015 menjadi weather_2015.csv
5. `csvstack data/weather_2014.csv data/weather_2015.csv > data/weather.csv` Menggabungkan weather_2014.csv dan weather_2015.csv menjadi 1 file csv
6. `rm data/weather_data.xlsx` Hapus file weather_data.xlsx
7. `csvlook data/weather.csv | sample -r 0.3 > data/sample_weather.csv` Sampling weather.csv dengan proporsi 0.3 dari total file dan simpan di file sample_weather.csv
