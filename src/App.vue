<template>
    <div id="app">
        <header>
            <person name="Orges Mihaj" profession="Web Developer"></person>
        </header>

        <about resumeURL="http://orgesmihaj.com/src/assets/files/Orges_Mihaj_resume.pdf">
            Hello! I am Orges Mihaj. Web Developer with over 3 years of experience specializing in front end development. Experienced with all stages of the development cycle for dynamic web projects. Having knowledge in HTML5, CSS3, SASS, JSON, JavaScript, Vue.js, JQuery, AngularJS, Bootstrap, PHP, Laravel, Python, Django.
        </about>

        <timeline name="Work Experience" id="jobs">
            <record role="Instructor"
                 employer="Almooc"
                 employerURL="http://almooc.com/"
                 period="Sep 2016 – Nov 2016"
                 description="Conducted in-depth tutorials on validating and processing forms with JavaScript and PHP for the largest MOOC in Albania.">
            </record>

            <record role="Web Developer"
                 employer="Freelance"
                 employerURL="#"
                 period="2015 – present"
                 description ="Developed various web application for different clients. Used Laravel, PHP framework, to create back-end of applications and HTML5, CSS3, JavaScript, JQuery, AngularJS, VueJS Bootstrap for front-end. Worked in Agile development environment. Optimized web images by using Photoshop CC.">
            </record>

            <record role="Intern, Web Developer"
                 employer="RealVisualz"
                 employerURL="http://www.realvisualz.com/RV/"
                 period="Dec 2015 – Mar 2016"
                 description="Conducted in-depth tutorials on validating and processing forms with JavaScript and PHP for the largest MOOC in Albania.">
            </record>
        </timeline>

        <portfolio>
            <project
                name="Albanian International School"
                description="A content management system (CMS) website for an international school in Tirana, Albania. "
                website="ais-tirana.org"
                websiteURL="http://ais-tirana.org/"
                logo="src/assets/img/portfolio/AIS-logo.png"
                imagePath="src/assets/img/portfolio/ais.jpg"
            ></project>

            <project
                name="Rootonym"
                description="A cross-word type web game with 2 difficulty levels where points were awarded in a time-constraint environment."
                website="m.iwin.com/game/play/rootonym"
                websiteURL="http://m.iwin.com/game/play/rootonym"
                logo="src/assets/img/portfolio/rootonym-logo.png"
                imagePath="src/assets/img/portfolio/rootonym.jpg"
            ></project>
        </portfolio>

        <timeline name="Education" id="education">
            <record institution="Harry T. Fultz Institute, Tirana, Albania"
                    website="harryfultz.edu.al"
                    websiteURL="http://www.harryfultz.edu.al"
                    period="2013 – present"
                    description="General professional training in electronics field which consists of maintaining, repairing,
and programming of electronic devices. Projects included electronic schema analysis,
programming microcontroller like Arduino, and problem-solving algorithms."
            ></record>

            <record institution="Washington Education in Albania/Kosovo"
                    website="www.wea.al"
                    websiteURL="http://www.wea.al"
                    period="2014 – present"
                    description="Online-based school committed to train Albanian students in software engineering. Recipient
of scholarship provided by Real Visualz LLC Bellevue WA, USA. Coursework included
entrepreneurship, developing ideas and design concepts, object-oriented languages ideas and
concepts, building dynamic webpages, and project management."
            ></record>
        </timeline>

        <footer class="footer">
            <p>© orgesmihaj.com by <a href="http://orgesmihaj.com">Orges Mihaj</a>.</p>
            <p>orges.mihaj@hotmail.com</p>
            <p>
                <a class="icon" target="_blank" href="https://www.linkedin.com/in/orgesmihaj"><i class="fa fa-linkedin" aria-hidden="true"></i></a>
                <a class="icon" target="_blank" href="https://github.com/OrgesMihaj"><i class="fa fa-github" aria-hidden="true"></i></a>
            </p>
        </footer>
    </div>
</template>

<script>

import Person    from './components/Person.vue';
import About     from './components/About.vue';
import Timeline  from './components/Timeline.vue';
import Record    from './components/Record.vue';
import Portfolio from './components/Portfolio.vue';
import Project   from './components/Project.vue';

export default {
    name: 'app',

    components: {
        Person, About, Timeline, Record, Portfolio, Project
    },

    data () {
        return {
            name: "", profession: "",

            resumeURL: "",

            name:"", id: "", role: "", employer: "", employerURL: "", period: "", website: "", institution: "", websiteURL: "",
            imagePath: "", logo: ""
        }
    }


}
</script>

<style lang="scss">

    @import "assets/scss/master";
    @import "assets/scss/app";

    body {
        font-family: $font-family;
    }
</style>
