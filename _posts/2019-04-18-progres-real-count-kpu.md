---
title: Progres dari Real Count KPU pada Pemilihan Presiden 2019
---

<script src="https://cdnjs.cloudflare.com/ajax/libs/moment.js/2.13.0/moment.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/2.1.3/jquery.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/Chart.js/2.8.0/Chart.bundle.js"></script>

KPU telah memulai proses *real count* Pemilu 2019 sejak tanggal
17 April 2019 lalu. Saya mencoba untuk merekam kemajuan (*progress*)
dari *real count* KPU tersebut.

Lihat [*disclaimer* (sangkalan)](#disclaimer-sangkalan).

Rincian Data
---

| *Last Updated*     | 02 May 2019 22:27:36 WITA  |
| *Last Version*[^1] | 02 May 2019 22:15:04 WITA  |
| *Last Progress*    | 62,61339% dari 813.350 TPS |

<!--<p id="countup"></p>-->
<p id="countdown"></p>

<script>
const now = moment();
//let startcount = moment("17 Apr 2019", "DD MMM YYYY");
let endcount = moment("23 May 2019", "DD MMM YYYY");
let diffdown = endcount.diff(now, 'day');
	if (diffdown < 0) {
	diffdown = 0;
	}
//let diffup = startcount.diff(now, 'day');
let counterdown = document.getElementById('countdown');
counterdown.innerHTML = 'Rekapitulasi suara diperkirakan berakhir dalam ' + diffdown + ' hari.';
//let counterup = document.getElementById('countup');
//counterup.innerHTML = 'Rekapitulasi suara telah berlangsung selama ' + Math.abs(diffup) + ' hari.';
</script>

<!--
| 					 | **Provinsi Sulawesi Selatan** |
|--------------------|-------------------------------|
| *Last Visit*  	 | 20 Apr 2019 17:54:05 WITA	 |
| *Last Version*	 | 20 Apr 2019 17:45:02 WITA	 |
| *Last Progress*    | 5,90021% dari 26.355 TPS      |
-->

[^1]: Versi dari data KPU saat saya terakhir kali memperbarui data.

*Records*
---

[Lihat tabulasi data di Google Spreadsheets.](<https://docs.google.com/spreadsheets/d/1_FrbBFEcgaX2rU-BDzjBi-qhuVjWN3oLcfv1lrSBtks/edit?usp=sharing>){:target="_blank"}

<canvas id="canvas" width="100%" height="85%"></canvas>
<script> //Code adapted from https://embed.plnkr.co/JOI1fpgWIS0lvTeLUxUp/
	
    var timeFormat = 'YYMMDD HHmm ss';
    
	Chart.defaults.global.defaultFontFamily = 'Source Sans Pro';
	
	function divideVotes(vote) {
		var dvote = vote / 1000000;
		return dvote.toLocaleString("id-ID");
	}
	
    var config = {
        type:    'line',
        data:    {
            datasets: [
                {
                    label: "Jokowi-Amin",
                    data: [
                    { x: "190418 0000 00", y: NaN },
                    { x: "190418 1030 03", y: 130952 },
                    { x: "190418 1045 03", y: 141898 },
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
                    { x: "190419 0845 02", y: 1158171 },
                    { x: "190419 1100 03", y: 1182353 },
                    { x: "190419 1330 03", y: 1460232 },
                    { x: "190419 1430 03", y: 1652105 },
                    { x: "190419 1630 03", y: 2017709 },
                    { x: "190419 1745 03", y: 2062784 },
                    { x: "190419 1915 02", y: 2308495 },
                    { x: "190419 2015 03", y: 2527064 },
                    { x: "190419 2145 02", y: 2728037 },
                    { x: "190419 2315 02", y: 3201594 },
                    { x: "190420 0015 03", y: 3493887 },
                    { x: "190420 0400 03", y: 3843519 },
                    { x: "190420 0600 03", y: 3855607 },
                    { x: "190420 0700 03", y: 3870392 },
                    { x: "190420 0830 03", y: 3943595 },
                    { x: "190420 1000 02", y: 3966642 },
                    { x: "190420 1245 03", y: 3974811 },
                    { x: "190420 1415 03", y: 3974985 },
                    { x: "190420 1545 03", y: 3974985 },
                    { x: "190420 1745 02", y: 4074791 },
                    { x: "190420 1845 03", y: 4292323 },
                    { x: "190420 2100 03", y: 4654040 },
                    { x: "190421 0545 03", y: 6524078 },
                    { x: "190421 0645 03", y: 6584978 },
                    { x: "190421 1000 03", y: 6817504 },
                    { x: "190421 1315 03", y: 7943509 },
                    { x: "190421 1515 03", y: 8623734 },
                    { x: "190421 1645 03", y: 9061929 },
                    { x: "190421 2030 03", y: 9899149 },
                    { x: "190421 2115 03", y: 9992917 },
                    { x: "190421 2130 03", y: 10003485 },
                    { x: "190421 2300 03", y: 10101749 },
                    { x: "190422 0030 03", y: 10172959 },
                    { x: "190422 0530 02", y: 10939017 },
                    { x: "190422 0645 03", y: 11267315 },
                    { x: "190422 0745 03", y: 11519680 },
                    { x: "190422 1200 03", y: 12596716 },
                    { x: "190422 1345 03", y: 13034658 },
                    { x: "190422 1530 03", y: 13462677 },
                    { x: "190422 1745 05", y: 13868892 },
                    { x: "190422 1915 05", y: 14087278 },
                    { x: "190422 2130 05", y: 14531078 },
                    { x: "190422 2300 05", y: 14809611 },
                    { x: "190423 0515 06", y: 15664144 },
                    { x: "190423 0930 06", y: 16303798 },
                    { x: "190423 1145 04", y: 16664317 },
                    { x: "190423 1230 04", y: 16737534 },
                    { x: "190423 2000 05", y: 18789350 },
                    { x: "190423 2100 05", y: 19198789 },
                    { x: "190423 2300 05", y: 20249187 },
                    { x: "190424 0045 03", y: 21211315 },
                    { x: "190424 0600 04", y: 22573499 },
                    { x: "190424 1300 03", y: 24039659 },
                    { x: "190424 1500 03", y: 24647140 },
                    { x: "190424 1715 04", y: 25155872 },
                    { x: "190424 1800 03", y: 25279837 },
                    { x: "190424 2045 04", y: 25800354 },
                    { x: "190424 2330 04", y: 26300100 },
                    { x: "190425 0515 04", y: 27192669 },
                    { x: "190425 0915 03", y: 27711665 },
                    { x: "190425 1100 05", y: 28222651 },
                    { x: "190425 1300 04", y: 28802876 },
                    { x: "190425 1500 05", y: 28985745 },
                    { x: "190425 1645 05", y: 29154856 },
                    { x: "190425 2045 05", y: 29624518 },
                    { x: "190426 0030 05", y: 30032869 },
                    { x: "190426 0230 05", y: 30281469 },
                    { x: "190426 0615 03", y: 30685752 },
                    { x: "190426 0945 03", y: 30987004 },
                    { x: "190426 1230 03", y: 31138461 },
                    { x: "190426 1600 04", y: 32386391 },
                    { x: "190426 1845 04", y: 33138454 },
                    { x: "190426 2115 05", y: 33469524 },
                    { x: "190427 0400 05", y: 34596471 },
                    { x: "190427 0945 05", y: 35333224 },
                    { x: "190427 1030 04", y: 35541055 },
                    { x: "190427 1545 05", y: 36443052 },
                    { x: "190427 1815 04", y: 36729244 },
                    { x: "190427 2115 05", y: 37215584 },
                    { x: "190428 0000 04", y: 37614971 },
                    { x: "190428 0845 05", y: 39349209 },
                    { x: "190428 1145 04", y: 39796262 },
                    { x: "190428 1545 03", y: 40552113 },
                    { x: "190428 1715 04", y: 40655967 },
                    { x: "190428 2000 05", y: 41040169 },
                    { x: "190428 2145 05", y: 41357974 },
                    { x: "190429 0500 05", y: 42591437 },
                    { x: "190429 0915 04", y: 42890589 },
                    { x: "190429 1200 05", y: 43636286 },
                    { x: "190429 1330 05", y: 43998110 },
                    { x: "190429 1530 05", y: 44345365 },
                    { x: "190429 1715 03", y: 44577612 },
                    { x: "190429 2000 04", y: 45085748 },
                    { x: "190429 2130 05", y: 45458225 },
                    { x: "190429 2315 03", y: 45757242 },
                    { x: "190430 0515 04", y: 46471394 },
                    { x: "190430 0819 32", y: 46621998 },
                    { x: "190430 1200 03", y: 47207002 },
                    { x: "190430 1515 04", y: 48021644 },
                    { x: "190430 1730 06", y: 48693771 },
                    { x: "190430 2115 05", y: 49518724 },
                    { x: "190501 0515 05", y: 50196339 },
                    { x: "190501 1145 04", y: 50486521 },
                    { x: "190501 1445 05", y: 50891401 },
                    { x: "190501 1600 05", y: 51053586 },
                    { x: "190501 1730 03", y: 51227541 },
                    { x: "190501 2230 03", y: 51876344 },
                    { x: "190502 0015 04", y: 52062338 },
                    { x: "190502 0500 04", y: 52301923 },
                    { x: "190502 0915 05", y: 52358693 },
                    { x: "190502 1315 03", y: 52730529 },
                    { x: "190502 1545 04", y: 52955686 },
                    { x: "190502 1700 05", y: 53207285 },
                    { x: "190502 2045 04", y: 53534444 },
                    { x: "190502 2215 04", y: 53613575 },
                    { x: "190503 0000 00", y: NaN }
                    ],
                    fill: false,
                    backgroundColor: 'rgba(253,106,2,0.5)',
                    borderColor: 'orange',
                    pointBackgroundColor: 'orange',
                    pointRadius: 2
                },
                {
                    label: "Prabowo-Sandi",
                    data: [
                    { x: "190418 0000 00", y: NaN },
                    { x: "190418 1030 03", y: 93168 },
                    { x: "190418 1045 03", y: 98766 },
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
                    { x: "190419 0845 02", y: 897441 },
                    { x: "190419 1100 03", y: 916583 },
                    { x: "190419 1330 03", y: 1157239 },
                    { x: "190419 1430 03", y: 1323415 },
                    { x: "190419 1630 03", y: 1639061 },
                    { x: "190419 1745 03", y: 1678115 },
                    { x: "190419 1915 02", y: 1894876 },
                    { x: "190419 2015 03", y: 2065691 },
                    { x: "190419 2145 02", y: 2242280 },
                    { x: "190419 2315 02", y: 2650827 },
                    { x: "190420 0015 03", y: 2887964 },
                    { x: "190420 0400 03", y: 3186560 },
                    { x: "190420 0600 03", y: 3195689 },
                    { x: "190420 0700 03", y: 3203292 },
                    { x: "190420 0830 03", y: 3237714 },
                    { x: "190420 1000 02", y: 3260762 },
                    { x: "190420 1245 03", y: 3267011 },
                    { x: "190420 1415 03", y: 3267585 },
                    { x: "190420 1545 03", y: 3267585 },
                    { x: "190420 1745 02", y: 3351052 },
                    { x: "190420 1845 03", y: 3526024 },
                    { x: "190420 2100 03", y: 3819116 },
                    { x: "190421 0545 03", y: 5460061 },
                    { x: "190421 0645 03", y: 5536979 },
                    { x: "190421 1000 03", y: 5761443 },
                    { x: "190421 1315 03", y: 6775380 },
                    { x: "190421 1515 03", y: 7306995 },
                    { x: "190421 1645 03", y: 7661540 },
                    { x: "190421 2030 03", y: 8281902 },
                    { x: "190421 2115 03", y: 8347297 },
                    { x: "190421 2130 03", y: 8357386 },
                    { x: "190421 2300 03", y: 8436329 },
                    { x: "190422 0030 03", y: 8515012 },
                    { x: "190422 0530 02", y: 9101848 },
                    { x: "190422 0645 03", y: 9358271 },
                    { x: "190422 0745 03", y: 9522373 },
                    { x: "190422 1200 03", y: 10379989 },
                    { x: "190422 1345 03", y: 10739746 },
                    { x: "190422 1530 03", y: 11041582 },
                    { x: "190422 1745 05", y: 11373470 },
                    { x: "190422 1915 05", y: 11542350 },
                    { x: "190422 2130 05", y: 11878308 },
                    { x: "190422 2300 05", y: 12112135 },
                    { x: "190423 0515 06", y: 12889427 },
                    { x: "190423 0930 06", y: 13335122 },
                    { x: "190423 1145 04", y: 13573048 },
                    { x: "190423 1230 04", y: 13629609 },
                    { x: "190423 2000 05", y: 15257189 },
                    { x: "190423 2100 05", y: 15623028 },
                    { x: "190423 2300 05", y: 16377736 },
                    { x: "190424 0045 03", y: 17040090 },
                    { x: "190424 0600 04", y: 18163090 },
                    { x: "190424 1300 03", y: 19184873 },
                    { x: "190424 1500 03", y: 19588085 },
                    { x: "190424 1715 04", y: 19941082 },
                    { x: "190424 1800 03", y: 20022609 },
                    { x: "190424 2045 04", y: 20414721 },
                    { x: "190424 2330 04", y: 20795976 },
                    { x: "190425 0515 04", y: 21574881 },
                    { x: "190425 0915 03", y: 21928482 },
                    { x: "190425 1100 05", y: 22195224 },
                    { x: "190425 1300 04", y: 22579081 },
                    { x: "190425 1500 05", y: 22698526 },
                    { x: "190425 1645 05", y: 22817788 },
                    { x: "190425 2045 05", y: 23159091 },
                    { x: "190426 0030 05", y: 23477194 },
                    { x: "190426 0230 05", y: 23681133 },
                    { x: "190426 0615 03", y: 24042249 },
                    { x: "190426 0945 03", y: 24270678 },
                    { x: "190426 1230 03", y: 24364314 },
                    { x: "190426 1600 04", y: 25135659 },
                    { x: "190426 1845 04", y: 25694794 },
                    { x: "190426 2115 05", y: 25961818 },
                    { x: "190427 0400 05", y: 26861844 },
                    { x: "190427 0945 05", y: 27248748 },
                    { x: "190427 1030 04", y: 27551292 },
                    { x: "190427 1545 05", y: 28213323 },
                    { x: "190427 1815 04", y: 28411517 },
                    { x: "190427 2115 05", y: 28765758 },
                    { x: "190428 0000 04", y: 29077648 },
                    { x: "190428 0845 05", y: 30396969 },
                    { x: "190428 1145 04", y: 30766428 },
                    { x: "190428 1545 03", y: 31418250 },
                    { x: "190428 1715 04", y: 31514186 },
                    { x: "190428 2000 05", y: 31829050 },
                    { x: "190428 2145 05", y: 32131072 },
                    { x: "190429 0500 05", y: 33171813 },
                    { x: "190429 0915 04", y: 33423040 },
                    { x: "190429 1200 05", y: 33962083 },
                    { x: "190429 1330 05", y: 34248539 },
                    { x: "190429 1530 05", y: 34576562 },
                    { x: "190429 1715 03", y: 34765340 },
                    { x: "190429 2000 04", y: 35188290 },
                    { x: "190429 2130 05", y: 35418100 },
                    { x: "190429 2315 03", y: 35662474 },
                    { x: "190430 0515 04", y: 36232587 },
                    { x: "190430 0819 32", y: 36367976 },
                    { x: "190430 1200 03", y: 36875475 },
                    { x: "190430 1515 04", y: 37579269 },
                    { x: "190430 1730 06", y: 38181337 },
                    { x: "190430 2115 05", y: 38825824 },
                    { x: "190501 0515 05", y: 39422531 },
                    { x: "190501 1145 04", y: 39669587 },
                    { x: "190501 1445 05", y: 40013708 },
                    { x: "190501 1600 05", y: 40151113 },
                    { x: "190501 1730 03", y: 40289340 },
                    { x: "190501 2230 03", y: 40743882 },
                    { x: "190502 0015 04", y: 40854051 },
                    { x: "190502 0500 04", y: 40992231 },
                    { x: "190502 0915 05", y: 41021408 },
                    { x: "190502 1315 03", y: 41337125 },
                    { x: "190502 1545 04", y: 41569208 },
                    { x: "190502 1700 05", y: 41765840 },
                    { x: "190502 2045 04", y: 42233069 },
                    { x: "190502 2215 04", y: 42315139 },
                    { x: "190503 0000 00", y: NaN }
                    ],
                    fill:  false,
                    backgroundColor: 'rgba(135,206,235,0.5)',
                    borderColor: 'skyblue',
                    pointBackgroundColor: 'skyblue',
                    pointRadius: 2
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
                        unit: 'day',
                        displayFormats: {
                        	hour: 'DD MMM HH:mm',
                        	day: 'DD MMM YYYY'
                        },
                        unitStepSize: 3,
                        format: timeFormat,
                        tooltipFormat: 'DD MMM YYYY HH:mm:ss'
                    },
                    scaleLabel: {
                        display:     true,
                        labelString: 'Tanggal/Versi (dalam WITA)'
                    }
                }],
                yAxes: [{
                    scaleLabel: {
                        display:     true,
                        labelString: 'Perolehan Suara'
                    },
                    ticks: {
                    	userCallback: function(value) {
                    			if (value == 0) {
                    				return divideVotes(value);
                    			}
                    		return divideVotes(value) + ' jt';
                    	}
                    }
                }]
            },
           tooltips: {  //Code taken from https://github.com/chartjs/Chart.js/issues/411#issuecomment-289196968
                enabled: true,

                callbacks: {
                        label: function (tooltipItems, data) {
                        return data.datasets[tooltipItems.datasetIndex].label + ': ' + tooltipItems.yLabel.toLocaleString("id-ID") + ' suara';
                    }
                }
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
    }
</script>

*Disclaimer* (Sangkalan)
---

**Situs ini tidak terafiliasi dengan Komisi Pemilihan Umum (KPU)
Republik Indonesia dan pihak-pihak lain dalam bentuk apapun.**

Saya melakukan proses perekaman secara manual dengan mengunjungi
[situs Info Publik Pemilu 2019 milik KPU](<https://pemilu2019.kpu.go.id/#/ppwp/hitung-suara/>){:target="_blank"}
dalam jangka waktu tertentu dan mencatat data di dalamnya.
Sebagai bukti, saya mengambil tangkapan layar saat berkunjung
ke situs KPU dan
[menyimpannya di *mega.nz*](<https://mega.nz/#F!QYBXGSxB!f_a_BKtplMGP6TOFUdAjbw>){:target="_blank"}.

Saya tidak dapat menjamin bahwa saya dapat memperbarui data di
atas secara rutin. *Saya juga tidak dapat menjamin bahwa data di
atas bebas dari kecurangan dan/atau aktivitas peretasan*.

Proses perekaman data dimulai tanggal 18 April 2019 dikarenakan
KPU baru memberikan *raw data* pada tanggal tersebut.

Merasa ada kesalahan pada data di atas? Segera
[buat *issue*](<https://github.com/qauland/qauland.github.io/issues/new>){:target="_blank"}
di repositori GitHub situs ini, atau beritahu saya melalui
[Twitter](<https://twitter.com/qauland>){:target="_blank"},
[Facebook](<https://fb.me/qauland>){:target="_blank"},
[Telegram](<https://t.me/qauland>){:target="_blank"}, dan/atau
[Discord](<https://discordapp.com>){:target="_blank"}: qauland#5976.

---Qaulan Ma'ruf Lira

---

