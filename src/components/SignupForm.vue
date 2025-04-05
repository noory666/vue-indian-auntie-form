<template>
    <div class="beech-me-lao bg-auntie-white">
        <form class="auntie-form" @submit.prevent="submit">
            <h1 class="auntieheading">{{ title }}</h1>
            <div class="auntiebox">
                <label class="auntie-bold">Email</label>
                <input @input="e => e.target.setCustomValidity('')"
                    @invalid="e => e.target.setCustomValidity('Didi, sahi wala email bharna. Nahi toh mere Kittu se bharwa lo.')"
                    class="auntie-input" type="email" v-model="mail" required>
            </div>
            <div class="auntiebox">
                <label class="auntie-bold">Confirm Email</label>
                <input @input="e => e.target.setCustomValidity('')"
                    @invalid="e => e.target.setCustomValidity('Didi, sahi wala email bharna. Nahi toh mere Kittu se bharwa lo.')"
                    class="auntie-input" type="email" v-model="mail_confirm" required>
            </div>
            <div class="auntiebox">
                <label class="auntie-bold">Password</label>
                <input minlength="8" @input="e => e.target.setCustomValidity('')"
                    @invalid="e => e.target.setCustomValidity('Sahi sa password bharna! Nahi to Ganpati@123 likh daalo.')"
                    class="auntie-input" type="password" v-model="passwd" required>
            </div>
            <div class="auntiebox">
                <label class="auntie-bold">Confirm Password</label>
                <input minlength="8" @input="e => e.target.setCustomValidity('')"
                    @invalid="e => e.target.setCustomValidity('Sahi sa password bharna! Nahi to Ganpati@123 likh daalo.')"
                    class="auntie-input" type="password" v-model="passwd_confirm" required>
            </div>
            <div class="auntiebox">
                <label class="auntie-bold">Gender</label>
                <select v-model="sex" class="choosy-auntie">
                    <option value="prefer_not">Mujhe Sharam Aati Hai Bataane Mein 🙈</option>
                    <option value="male">Aadmi</option>
                    <option value="female">Aorat</option>
                    <option value="non_binary">Dono Me Se Kuch Bhi Nahi</option>
                </select>
            </div>
            <div class="auntiebox">
                <label class="auntie-bold">Interests</label>
                <div class="flex gap-3 items-center">
                    <input v-model="interests" value="kitty_party" type="checkbox" class="h-5 w-5">
                    <label class="text-sm">Kitty Parties</label>
                </div>
                <div class="flex gap-3 items-center">
                    <input v-model="interests" value="serials" type="checkbox" class="h-5 w-5">
                    <label class="text-sm">TV Serials ( Dhum Tana Tana )</label>
                </div>
                <div class="flex gap-3 items-center">
                    <input v-model="interests" value="whatsapp" type="checkbox" class="h-5 w-5">
                    <label class="text-sm">WhatsApp University</label>
                </div>
                <div class="flex gap-3 items-center">
                    <input v-model="interests" value="puja" type="checkbox" class="h-5 w-5">
                    <label class="text-sm">Puja Samagri Management</label>
                </div>
                <div class="flex gap-3 items-center">
                    <input v-model="interests" value="tupperware" type="checkbox" class="h-5 w-5">
                    <label class="text-sm">Tupperware Hoarding</label>
                </div>
                <div class="flex gap-3 items-center">
                    <input v-model="interests" value="gossip" type="checkbox" class="h-5 w-5">
                    <label class="text-sm">Colony Gossip</label>
                </div>
                <div class="flex gap-3 items-center">
                    <input v-model="interests" value="biryani" type="checkbox" class="h-5 w-5">
                    <label class="text-sm">Biryani Tasting</label>
                </div>
                <div class="flex gap-3 items-center">
                    <input v-model="interests" value="matchmaking" type="checkbox" class="h-5 w-5">
                    <label class="text-sm">Freelance Matchmaking</label>
                </div>
                <div class="flex gap-3 items-center">
                    <input v-model="interests" value="forwarding" type="checkbox" class="h-5 w-5">
                    <label class="text-sm">Forwarding Good Morning Messages</label>
                </div>
                <div class="flex gap-3 items-center">
                    <input v-model="interests" value="mehendi" type="checkbox" class="h-5 w-5">
                    <label class="text-sm">Festival Mehendi Planning</label>
                </div>
            </div>

            <div class="auntiebox">
                <label class="auntie-bold">Tick Kardo</label>
                <div class="flex gap-3 items-center">
                    <input type="checkbox" class="h-5 w-5" v-model="sharmajison">
                    <label class="text-sm">Sharma ji ka ladka hoshiar hai.</label>
                </div>
                <div class="flex gap-3 items-center">
                    <input type="checkbox" class="h-5 w-5" v-model="biryani">
                    <label class="text-sm">I'm just here for the biryani.</label>
                </div>
                <div class="flex gap-3 items-center">
                    <input type="checkbox" class="h-5 w-5" v-model="responsibleaunty">
                    <label class="text-sm">Yes, I clicked without reading. Like always.</label>
                </div>
                <div class="flex gap-3 items-center">
                    <input type="checkbox" class="h-5 w-5" v-model="veryattentive">
                    <label class="text-sm">Chal na, tick maar de.</label>
                </div>
                <div class="flex gap-3 items-center">
                    <input type="checkbox" class="h-5 w-5" v-model="masterbluff">
                    <label class="text-sm">Pakka promise, I won't sue.</label>
                </div>
                <div class="flex gap-3 items-center">
                    <input type="checkbox" class="h-5 w-5" v-model="prayermagic">
                    <label class="text-sm">Shree Ganeshay Namah - Let's Go!</label>
                </div>
            </div>


            <div class="auntiebox">
                <div class="flex gap-3 items-center">
                    <input v-model="lucky" value=true name="lucky" type="radio" class="h-5 w-5">
                    <label class="text-sm">I'm feelin' like Whatsapp Forwarding</label>
                </div>
                <div class="flex gap-3 items-center">
                    <input v-model="lucky" value=false name="lucky" type="radio" class="h-5 w-5">
                    <label class="text-sm">I'm feelin' Rajpal Yadav</label>
                </div>
            </div>

            <div class="beech-me-lao">
                <button class="bg-black text-white auntie-bold rounded-full px-6 py-3">Submit</button>
            </div>
        </form>
    </div>
</template>

<script>
export default {
    data() {
        return {
            mail: 'jaya.desai@auntymail.in',
            mail_confirm: 'jaya.desai@auntymail.in',
            passwd: 'KittuKiMummy',
            passwd_confirm: 'KittuKiMummy',
            sex: 'female',
            interests: ['kitty_party', 'serials', 'whatsapp', 'puja', 'tupperware', 'gossip', 'biryani', 'matchmaking', 'forwarding', 'mehendi'],
            title: '',
            titles: ["Mummy Verified Rishtey", "Didi, Password To Daalo", "The Great Aunty Login Yatra", "ManglikMilaap.org Rejects Recovery Form", "Join the Kittyverse", "Puja & Passwords", "Register for Rasodey Ki Rajniti", "Enroll in WhatsApp University"],
            lucky: true,
            sharmajison: true,
            biryani: true,
            responsibleaunty: true,
            veryattentive: true,
            masterbluff: true,
            prayermagic: true,
        }
    },
    mounted() { this.title = this.titles[Math.floor(Math.random() * this.titles.length)] },
    methods: {
        setCustomMessage(input, message) { input.setCustomValidity(message) },
        validateForm() {
            const emailRegex = /^[a-zA-Z0-9._\-'"()]{4,}@[a-zA-Z0-9\-]{4,}\.[a-zA-Z]{2,18}$/
            if (!emailRegex.test(this.mail)) { alert ("Email format galat hai didi! Thoda dhyaan do."); return false }
            if (this.mail !== this.mail_confirm) { alert ("Email Confirm Wala Match Nahi Kar Raha."); return false }
            if (this.passwd.length < 8) { alert ("Password Kam-Se-Kam 8 Letter ka Hona Chahiye."); return false }
            if (this.passwd !== this.passwd_confirm) { alert ("Password Confirm Wala Match Nahi Kar Raha."); return false }
            if (!Array.isArray(this.interests)) { alert ("Interests Proper Array Hona Chahiye."); return false }
            if (this.interests.length < 4 || this.interests.length > 12) { alert ("Interests mein kam se kam 4 aur zyada se zyada 12 items hone chahiye."); return false }
            for (let item of this.interests) { if (typeof item !== 'string') { alert("Interests ke saare items string hone chahiye."); return false } }

            const auntyhoodVerified = [ this.lucky, this.sharmajison, this.biryani, this.responsibleaunty, this.veryattentive, this.masterbluff, this.prayermagic ].every(flag => flag === true)

            if (!auntyhoodVerified) {
                const failedAlerts = [
                    "💔 Beta, tumse na ho payega.\n\nAunty verification failed. Sasural waale ne mana kar diya.",
                    "📵 Arre nahi beti!\n\nYou forgot to tick a box and now Ramesh ki mummy is cancelling your kitty invite.",
                    "🚫 Tch tch... Aunty Association ne tumhara ID card reject kar diya hai. Try again with more biryani and belief.",
                    "💌 Beta, bina full tick ke WhatsApp University mein admission nahi milega. Forward karo ya bhool jao!",
                    "🛑 Oho! You forgot to tick one! Now your name has been removed from the Mehendi function guest list.",
                    "Auntyhood not confirmed!\n\nTupperware duty assigned to Rekha aunty instead.",
                    "🛶 Sorry beti, Ganpati Bappa bhi keh rahe hain — tick karo sab boxes ya ghar baitho.",
                    "😭 Arre na beti! Rajjo aunty ne bola: 'Isko toh main apne kitty mein bulaungi hi nahi!'",
                    "🧾 Form incomplete hai!\n\nRishta reject. Sasuraal ki chhoti maa ne mana kar diya.",
                    "🔮 Beta, auntyhood ka chakra incomplete hai.\n\nRekha aunty has revoked your spiritual license to gossip.",
                    "🚫 Beta, checklist incomplete!\n\nNo chai, no gossip, no snacks. You're on thin ice, didi.",
                    "📴 Alert! Alert!\n\nYou didn't tick all boxes. Now colony WhatsApp pe tumhara good morning post block ho gaya hai.",
                    "🥁 The entry is closed!\n\nThe aunty train left without you. Better luck in next Kalash Pooja.",
                    "😢 Sorry beti, ManglikMilaap.org pe auto-unmatch ho gaya.\n\nAunty verification failed.",
                    "📢 Auntyhood denied!\n\nColony ki gossip list se tumhara naam hata diya gaya. Tumse na ho payega.",
                ]
                alert(failedAlerts[Math.floor(Math.random() * failedAlerts.length)]);
                return false;
            }

            return true
        },
        submit () {
            if (!this.validateForm()) { return }
            const form = document.querySelector('form')
            form.submit()
            alert ('Congratulations! You’re now one of us. Password bhi bhoolna mat, warna Kittu ko bulana padega.')
        }
    }
}
</script>

<style>
.auntiebox {
    display: flex;
    flex-direction: column;
    gap: 0.5rem;
}

.auntieheading {
    text-align: center;
    font-size: 2rem;
    font-weight: 900;
}

.auntie-bold {
    font-weight: 900;
    font-size: 1.2rem;
}

.bg-auntie-white {
    background-color: #fff
}

.beech-me-lao {
    display: flex;
    justify-content: center;
    align-self: center;
}

.auntie-input {
    border: 1px solid black;
    border-radius: 9999px;
    padding: 0.25rem 0.75rem
}

.auntie-form {
    display: flex;
    flex-direction: column;
    gap: 2rem;
    margin: 3rem 0;
}

.choosy-auntie {
    border: 1px solid black;
    border-radius: 9999px;
    padding: 0.25rem 0.75rem;
}

.auntie-checkbox {
    display: flex;
    gap: 0.5rem;
    align-items: center;
}

select {
    -webkit-appearance: none;
    -moz-appearance: none;
    appearance: none;
    background-image: none
}

select::-ms-expand {
    display: none
}
</style>