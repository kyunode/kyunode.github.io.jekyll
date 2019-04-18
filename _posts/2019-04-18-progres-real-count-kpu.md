---
title: Progres dari Real Count KPU pada Pemilihan Presiden 2019
---

KPU telah memulai proses *real count* Pemilu 2019 sejak tanggal
17 April 2019 lalu. Saya mencoba untuk merekam kemajuan (*progress*)
dari *real count* KPU tersebut.

Lihat [*disclaimer* (sangkalan)](#disclaimer-sangkalan).

Rincian Data (saat terakhir kali saya berkunjung)
---

| *Last Visit*       | 18 Apr 2019 17:52:23   |
| *Last Version* 	 | 18 Apr 2019 17:45:03   | 
| *Last Progress*    | 0,68544%				  |
| TPS				 | 5.575 dari 813.350 TPS |

*Records*
---

Sajian data dalam bentuk tabel akan menyusul.

<script src="http://cdnjs.cloudflare.com/ajax/libs/moment.js/2.13.0/moment.min.js"></script>
<script src="http://cdnjs.cloudflare.com/ajax/libs/jquery/2.1.3/jquery.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/Chart.js/2.4.0/Chart.bundle.js"></script>
<canvas id="canvas" width="800" height="600"></canvas>
<script> //Code adapted from https://embed.plnkr.co/JOI1fpgWIS0lvTeLUxUp/
	
    var timeFormat = 'YYMMDD HHmm ss';
    
	Chart.defaults.global.defaultFontFamily = 'Source Sans Pro';
	
    var config = {
        type:    'line',
        data:    {
            datasets: [
                {
                    label: "Jokowi-Amin",
                    data: [
                    { x: "190418 1030 03", y: 130952 },
                    { x: "190418 1045 03", y: 141898 },
                    { x: "190418 1200 03", y: 197869 },
                    { x: "190418 1230 03", y: 214553 },
                    { x: "190418 1300 03", y: 260891 },
                    { x: "190418 1345 03", y: 296910 },
                    { x: "190418 1430 03", y: 336692 },
                    { x: "190418 1515 03", y: 403079 },
                    { x: "190418 1615 03", y: 482172 },
                    { x: "190418 1700 03", y: 535366 },
                    { x: "190418 1745 03", y: 610654 }
                    ],
                    fill: false,
                    borderColor: 'orange'
                },
                {
                    label: "Prabowo-Sandi",
                    data: [
                    { x: "190418 1030 03", y: 93168 },
                    { x: "190418 1045 03", y: 98766 },
                    { x: "190418 1200 03", y: 134808 },
                    { x: "190418 1230 03", y: 146216 },
                    { x: "190418 1300 03", y: 173138 },
                    { x: "190418 1345 03", y: 202217 },
                    { x: "190418 1430 03", y: 230570 },
                    { x: "190418 1515 03", y: 278317 },
                    { x: "190418 1615 03", y: 344762 },
                    { x: "190418 1700 03", y: 389656 },
                    { x: "190418 1745 03", y: 447461 }
                    ],
                    fill:  false,
                    borderColor: 'skyblue'
                }
            ]
        },
        options: {
            responsive: true,
            title:      {
                display: true,
                text:    "Hasil Perekaman Data Real Count KPU 2019",
                fontSize: 18
            },
            scales:     {
                xAxes: [{
                    type:       "time",
                    time:       {
                        unit: 'hour',
                        displayFormats: {
                        	hour: 'DD MMM HH:mm'
                        },
                        format: timeFormat,
                        tooltipFormat: 'DD MMM YYYY HH:mm:ss'
                    },
                    scaleLabel: {
                        display:     true,
                        labelString: 'Tanggal/Versi'
                    }
                }],
                yAxes: [{
                    scaleLabel: {
                        display:     true,
                        labelString: 'Jumlah Surat Suara'
                    }
                }]
            },
            elements: {
            	line: {
                	tension: 0 // disables bezier curves
            	}
        	},
        	legend: {
        		labels: {
        			fontSize: 14
        		}
        	}
        }
    };

    window.onload = function () {
        var ctx       = document.getElementById("canvas").getContext("2d");
        window.myLine = new Chart(ctx, config);
    };
</script>

*Disclaimer* (Sangkalan)
---

Proses perekaman dilakukan secara manual dengan mengunjungi
[situs Info Publik Pemilu 2019 milik KPU](<https://pemilu2019.kpu.go.id/#/ppwp/hitung-suara/>)
dalam jangka waktu tertentu dan mencatat data di dalamnya.
Sebagai bukti, saya mengambil tangkapan layar saat berkunjung
ke situs KPU.

Saya tidak dapat menjamin bahwa saya dapat memperbarui data di
atas secara rutin.

Proses perekaman dimulai tanggal 18 April 2019 dikarenakan KPU
baru memberikan *raw data* pada tanggal tersebut.
