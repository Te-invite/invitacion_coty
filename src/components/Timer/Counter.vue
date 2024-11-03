<script>

export default {
    name: 'Counter',
    props: ['year', 'month', 'date', 'hour', 'minute', 'second', 'millisecond'],
    data() {
        return {
            displayDays: 0,
            displayHours: 0,
            displayMinutes: 0 ,
            displaySeconds: 0,
            loaded: false,
            expired: false,
            d:"Días",
            h:"Hs.",
            m:"Min.",
            s:"Seg.",
            title:"14 DE DICIEMBRE DE 2024",
            title1:"¡LISTOS PARA FESTEJAR?"

        };
    },
    computed: {
        _seconds() {
            return 1000;
        },
        _minutes() {
            return this._seconds * 60;
        },
        _hours() {
            return this._minutes * 60;
        },
        _days() {
            return this._hours * 24;
        },
        end() {
            return new Date(
                this.year,
                this.month - 1, // Los meses en JavaScript van de 0 a 11
                this.date,
                this.hour,
                this.minute,
                this.second,
                this.millisecond
            );
        }
    },
    mounted() {
        this.showRemaining();
    },
    methods: {
        formatNum(num) {
            return num < 10 ? '0' + num : num;
        },
        showRemaining() {
            const timer = setInterval(() => {
                const now = new Date();
                const distance = this.end.getTime() - now.getTime();

                if (distance < 0) {
                    clearInterval(timer);
                    this.expired = true;
                    this.loaded = true;
                    return;
                }

                const days = Math.floor(distance / this._days);
                const hours = Math.floor((distance % this._days) / this._hours);
                const minutes = Math.floor((distance % this._hours) / this._minutes);
                const seconds = Math.floor((distance % this._minutes) / this._seconds);

                this.displayMinutes = this.formatNum(minutes);
                this.displaySeconds = this.formatNum(seconds);
                this.displayHours = this.formatNum(hours);
                this.displayDays = this.formatNum(days);
                this.loaded = true;
            }, 1000);
        }
    }
};
</script>

<template>
    <div v-if="loaded" class="container">
        <section class="title__counter">
            <h1 class="counter__txt" >{{ title }}</h1>
            <h3 v-show="!expired" class="counter__txt1" >{{ title1 }}</h3>
            <h3 v-show="expired" class="counter__txt" ></h3>
        </section>
        
        <section class="counter__container">
            <div class="counter__content dia">
                {{ displayDays }}
                <span class="counter__label">{{ d }}</span>
            </div>

            <div class="counter__content hora">
                {{ displayHours }}
                <span class="counter__label">{{ h }}</span>
            </div>
            <div class="counter__content minuto">
                {{ displayMinutes }}
                <span class="counter__label">{{ m }}</span>
            </div>
            <div class="counter__content segundos">
                {{ displaySeconds }}
                <span class="counter__label">{{ s }}</span>
            </div>
        </section>

    </div>
</template>

<style scoped>
.container{
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    width: 100%;
    height: 100%;
}

.counter__container,
.counter__label {
    color: var(--second-text-color);
    font-family: var(--body-font);
}

.counter__txt{
    font-size: 1.2rem;
    text-align: center;
    color: var(--second-text-color);
    font-family: var(--body-font);
    font-weight: normal;
    line-height: 80%;
}
.counter__txt1{
    font-size: 1rem;
    text-align: center;
    color: var(--second-text-color);
    font-family: var(--body-font);
    font-weight: lighter;
    line-height: 80%;
    margin-bottom:1rem;
}

.counter__container {
    display: flex;
    justify-content: center;
    flex-direction: row;
    align-items: center;
    width: 90%;
    height:100%;
    font-family: var(--title-font);
    font-weight: 600;
    font-size:1.3rem;
    line-height: 80%;
}

.counter__content {/*... */
    width: 50px;
    height:70%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}

.dia,
.hora,
.minuto {
    border-right: 1px solid var(--second-text-color); /*Separadores */
}

.counter__label {
    font-family: var(--body-font);
    font-size: .5rem;
    font-weight: normal;
    text-align: center;
}
@media (min-width: 768px) and (max-width: 991px){
    .container{
        width:100%;
        height: 100%;
    }
   .counter__container{
    font-size: 2.4rem;
    line-height: 70%;
   }
   .counter__content{
    width:15%;
   }
    .counter__txt{
        font-size: 2.2rem;
    }
    .counter__txt1{
        font-size: 2rem;
    }
    .counter__label {
        font-size: .7rem;
    }
    
}
@media (min-width: 1025px) {
    .container{
        width:100%;
        height: 100%;
    }
    .counter__content {/*... */
        width: 100%;
        height:80%;
        margin-top:1rem;
    }
   .counter__container{
    font-size: 4.5rem;
    line-height: 50%;
   }
    .counter__txt{
        font-size: 3.5rem;
    }
    .counter__txt1{
        font-size: 2.5rem;
    }
    .counter__label {
        font-size: 1.2rem;
    }
}
</style>