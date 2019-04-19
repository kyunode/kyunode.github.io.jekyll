---
title: Progres dari Real Count KPU pada Pemilihan Presiden 2019
---

KPU telah memulai proses *real count* Pemilu 2019 sejak tanggal
17 April 2019 lalu. Saya mencoba untuk merekam kemajuan (*progress*)
dari *real count* KPU tersebut.

Lihat [*disclaimer* (sangkalan)](#disclaimer-sangkalan).

Rincian Data
---

| 					 | **Tingkat Nasional**		  | **Provinsi Sulawesi Selatan** |
|--------------------|----------------------------|-------------------------------|
| *Last Visit*[^1]   | 19 Apr 2019 08:52:24 WITA  | 19 Apr 2019 08:52:24 WITA	  |
| *Last Version*[^2] | 19 Apr 2019 08:45:02 WITA  | 19 Apr 2019 08:45:02 WITA	  |
| *Last Progress*    | 1,32489% dari 813.350 TPS  | 1,36976% dari 26.355 TPS      |

[^1]: Kapan terakhir kali saya mengunjungi situs KPU.

[^2]: Versi dari data KPU saat saya terakhir kali mengunjungi situs KPU.

*Records*
---

Sajian data dalam bentuk tabel akan menyusul.

<script src="http://cdnjs.cloudflare.com/ajax/libs/moment.js/2.13.0/moment.min.js"></script>
<script src="http://cdnjs.cloudflare.com/ajax/libs/jquery/2.1.3/jquery.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/Chart.js/2.8.0/Chart.bundle.js"></script>
<canvas id="canvas" width="100%" height="85%"></canvas>
<script> //Code adapted from https://embed.plnkr.co/JOI1fpgWIS0lvTeLUxUp/
	
    var timeFormat = 'YYMMDD HHmm ss';
    
	Chart.defaults.global.defaultFontFamily = 'Source Sans Pro';
	
	function divideVotes(vote) {
		var dvote = vote / 1000000;
		return (dvote);
	}
	
    var config = {
        type:    'line',
        data:    {
            datasets: [
                {
                    label: "Jokowi-Amin",
                    data: [
                    { x: "190418 1000 00", y: NaN },
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
                    { x: "190418 1745 03", y: 610654 },
                    { x: "190418 2015 03", y: 723660 },
                    { x: "190418 2145 02", y: 741400 },
                    { x: "190418 2215 03", y: 766633 },
                    { x: "190419 0015 03", y: 945947 },
                    { x: "190419 0500 03", y: 1131661 },
                    { x: "190419 0645 03", y: 1136153 },
                    { x: "190419 0845 02", y: 1158171 }
                    ],
                    fill: false,
                    backgroundColor: 'rgba(253,106,2,0.5)',
                    borderColor: 'orange',
                    pointBackgroundColor: 'orange'
                },
                {
                    label: "Prabowo-Sandi",
                    data: [
                    { x: "190418 1000 00", y: NaN },
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
                    { x: "190418 1745 03", y: 447461 },
                    { x: "190418 2015 03", y: 534148 },
                    { x: "190418 2145 02", y: 548095 },
                    { x: "190418 2215 03", y: 570742 },
                    { x: "190419 0015 03", y: 722875 },
                    { x: "190419 0500 03", y: 873200 },
                    { x: "190419 0645 03", y: 878541 },
                    { x: "190419 0845 02", y: 897441 }
                    ],
                    fill:  false,
                    backgroundColor: 'rgba(135,206,235,0.5)',
                    borderColor: 'skyblue',
                    pointBackgroundColor: 'skyblue'
                }
            ]
        },
        options: {
            responsive: true,
            title:      {
                display: true,
                text:    ['Hasil Perekaman Data Real Count KPU 2019', 'Tingkat Nasional'],
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
                        unitStepSize: 3,
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
                        labelString: 'Perolehan Suara'
                    },
                    ticks: {
                    	userCallback: function(value) {
                    		return divideVotes(value) + 'jt';
                    	}
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
//
//    window.onload = function () {
//        var ctx       = document.getElementById("canvas").getContext("2d");
//        window.myLine = new Chart(ctx, config);
//    };
</script>

<br/>

<canvas id="canvasSulsel" width="100%" height="85%"></canvas>
<script> //Code adapted from https://embed.plnkr.co/JOI1fpgWIS0lvTeLUxUp/
	
    var timeFormat = 'YYMMDD HHmm ss';
    
	Chart.defaults.global.defaultFontFamily = 'Source Sans Pro';
	
	function divideVotesSulsel(votess) {
		var dvotess = votess / 1000;
		return (dvotess);
	}
	
    var config2 = {
        type:    'line',
        data:    {
            datasets: [
                {
                    label: "Jokowi-Amin",
                    data: [
                    { x: "190418 1000 00", y: NaN },
                    { x: "190418 2145 02", y: 17843 },
                    { x: "190418 2215 03", y: 18867 },
                    { x: "190419 0015 03", y: 25819 },
                    { x: "190419 0645 03", y: 29000 },
                    { x: "190419 0815 03", y: 29278 },
                    { x: "190419 0845 02", y: 29484 }
                    ],
                    fill: false,
                    backgroundColor: 'rgba(253,106,2,0.5)',
                    borderColor: 'orange',
                    pointBackgroundColor: 'orange'
                },
                {
                    label: "Prabowo-Sandi",
                    data: [
                    { x: "190418 1000 00", y: NaN },
                    { x: "190418 2145 02", y: 25168 },
                    { x: "190418 2215 03", y: 26661 },
                    { x: "190419 0015 03", y: 32762 },
                    { x: "190419 0645 03", y: 36827 },
                    { x: "190419 0815 03", y: 37407 },
                    { x: "190419 0845 02", y: 37465 }
                    ],
                    fill:  false,
                    backgroundColor: 'rgba(135,206,235,0.5)',
                    borderColor: 'skyblue',
                    pointBackgroundColor: 'skyblue'
                }
            ]
        },
        options: {
            responsive: true,
            title:      {
                display: true,
                text:    ['Hasil Perekaman Data Real Count KPU 2019', 'Wilayah Pemilihan Sulawesi Selatan'],
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
                        unitStepSize: 3,
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
                        labelString: 'Perolehan Suara'
                    },
                    ticks: {
                    	userCallback: function(value) {
                    		return divideVotesSulsel(value) + 'rb';
                    	}
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
        var ctxSulsel = document.getElementById("canvasSulsel").getContext("2d");
        window.myLine = new Chart(ctxSulsel, config2);
    }
</script>

*Disclaimer* (Sangkalan)
---

**Situs ini tidak terafiliasi dengan Komisi Pemilihan Umum (KPU)
Republik Indonesia dan pihak-pihak lain dalam bentuk apapun.**
Semua data yang ada di sini saya peroleh sendiri dari situs KPU.

Proses perekaman dilakukan secara manual dengan mengunjungi
[situs Info Publik Pemilu 2019 milik KPU](<https://pemilu2019.kpu.go.id/#/ppwp/hitung-suara/>){:target="_blank"}
dalam jangka waktu tertentu dan mencatat data di dalamnya.
Sebagai bukti, saya mengambil tangkapan layar saat berkunjung
ke situs KPU.

Saya tidak dapat menjamin bahwa saya dapat memperbarui data di
atas secara rutin. *Saya juga tidak dapat menjamin bahwa data di
atas bebas dari aktivitas peretasan*.

Proses perekaman data dimulai tanggal 18 April 2019 dikarenakan
KPU baru memberikan *raw data* pada tanggal tersebut.

Proses perekaman data untuk provinsi Sulawesi Selatan sedikit
terlambat (18 April 21:53) *karena saya baru pengen ngerekam
pukul segitu*. Khusus untuk provinsi Sulawesi Selatan, tidak ada
tangkapan layar (*screenshot*) yang saya ambil.

Merasa ada kesalahan pada data di atas? Segera beritahu saya lewat
[Twitter](<https://twitter.com/qauland>){:target="_blank"}, [Facebook](<https://fb.me/qauland>){:target="_blank"},
[Telegram](<https://t.me/qauland>){:target="_blank"}, dan/atau [Discord](<https://discordapp.com>){:target="_blank"}:
qauland#5976.

---Qaulan Ma'ruf Lira

---

