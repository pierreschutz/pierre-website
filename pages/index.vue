<template>
  <v-layout column justify-center align-center>
    <v-flex xs12 sm8 md6>
      <v-card class="main-card" color="theme2">
        <v-img class="white--text" height="400" src="/photo_berlin_pierre.jpg"></v-img>

        <v-card-title>Pierre Schutz</v-card-title>

        <v-card-text>
          Master Student in Data Science at EPFL (Swiss Federal Institute of Technology Lausanne).
          Vice-President and Treasurer of Blockchain Student Association at EPFL.
          Interested in Android mobile development, information security, decentralized systems, and Data Sciences.
        </v-card-text>

        <v-card-actions>
          <v-btn href="https://linkedin.com/in/pierreschutz" target="_blank" outlined>
            <v-icon>mdi-linkedin-box</v-icon>
            <v-label>LinkedIn</v-label>
          </v-btn>
          <v-btn href="https://github.com/pierreschutz" target="_blank" outlined>
            <v-icon>mdi-github-box</v-icon>
            GitHub
          </v-btn>
          <v-btn href="mailto:pierre.schutz@epfl.ch" target="_blank" outlined>
            <v-icon>mdi-email-box</v-icon>
            EMail
          </v-btn>

          <v-btn href="/Resume_Pierre_Schutz_EN.pdf" target="_blank" outlined>
            <v-icon>mdi-account-box</v-icon>
            Resume (CV)
          </v-btn>
        </v-card-actions>
      </v-card>

      <v-card class="main-card" color="theme2">
        <v-card-title>Experience</v-card-title>
        <v-card-text>

          <resume-item

            v-for="item in experience"
            :link="item.link"
            :color="item.color"
            :img_src="item.img_src"
            :title="item.title"
            :description="item.description"
            :company="item.company"
            :date="item.date"
            :location="item.location"

          ></resume-item>

        </v-card-text>
      </v-card>

      <v-card class="main-card" color="theme2">
        <v-card-title>Education</v-card-title>
        <v-card-text>

          <resume-item

            v-for="item in education"
            :color="item.color"
            :link="item.link"
            :img_src="item.img_src"
            :title="item.title"
            :description="item.description"
            :company="item.company"
            :date="item.date"
            :location="item.location"

          ></resume-item>


        </v-card-text>
      </v-card>

      <v-card class="main-card" color="theme2">
        <v-card-title>Leadership Activities</v-card-title>
        <v-card-text>

          <resume-item

            v-for="item in leadership"
            :color="item.color"
            :link="item.link"
            :img_src="item.img_src"
            :title="item.title"
            :description="item.description"
            :company="item.company"
            :date="item.date"
            :location="item.location"

          ></resume-item>

        </v-card-text>
      </v-card>


      <v-card class="main-card" color="theme2">
        <v-card-title>Projects</v-card-title>
        <v-card-text>

          <project-item

            v-for="item in projects"
            :color="item.color"
            :source_link="item.source_link"
            :description_link="item.description_link"
            :img_src="item.img_src"
            :title="item.title"
            :description="item.description"
            :keywords="item.keywords"

          ></project-item>


        </v-card-text>
      </v-card>


    </v-flex>
  </v-layout>
</template>

<script>
    import Logo from "~/components/Logo.vue";
    import VuetifyLogo from "~/components/VuetifyLogo.vue";
    import ResumeItem from "~/components/ResumeItem.vue";
    import ProjectItem from "../components/ProjectItem";

    export default {
        components: {
            Logo,
            VuetifyLogo,
            ResumeItem,
            ProjectItem
        },
        data: () => ({
            experience: [
                {
                    link:"https://inpher.io",
                    img_src: "/pierre-website_experience_2.png",
                    title: "Software Developer Intern",
                    company: "Inpher",
                    date: "June 2019 - August 2019",
                    location: "New York, USA",
                    description: "- Build a configuration's files manager interface that helps clients to create, read, edit and delete configurations file on their machine (Using Vue.js, Javascript, Node.js, Docker).\n" +
                        "- Acquire working knowledge about secret computing and privacy-preserving machine learning."

                },
                {
                    link:"https://je.epfl.ch",
                    img_src: "/pierre-website_experience_1.png",
                    title: "Technical Consultant, Software Engineer",
                    company: "Junior Enterprise EPFL",
                    date: "March 2018 - Present",
                    location: "Lausanne, Switzerland",
                    description: "- Consult on IT projects about databases, publish-subscribe pattern\n" +
                        "systems, mobile applications, e-commerce applications, SDK, web API.\n" +

                        "- Design specifications and time estimations for mobile or web development projects.\n" +

                        "- Test and analyze the behavior of mobile applications, and mobile frameworks (Matchmore.io).\n" +

                        "- Design and develop Android applications in Kotlin."

                },

                {
                    link:"https://epfl.ch",
                    img_src: "/pierre-website_experience_3.png",
                    title: "Teaching Assistant",
                    company: "Swiss Federal Institute of Technology (EPFL)",
                    date: "September 2017 - June 2018",
                    location: "Lausanne, Switzerland",
                    description: "Courses: \n- Advanced Information, Computation, and Communications I (Prof.  Arjen Lenstra).\n- Practice of Object-Oriented Programming (Prof.  Michel Schinz).\n- Advanced Information, Computation, and Communications II (Prof.  Bixio Rimoldi).\nTasks:\n- Help students to do their exercises, answer their questions, debug their code projects, correct and gradetheir homework."
                }
            ],

            education: [
                {
                    link: "https://epfl.ch",
                    img_src: "/pierre-website_education_1.png",
                    title: "Master of Science in Data Science",
                    company: "Swiss Federal Institute of Technology (EPFL)",
                    date: "September 2019 - July 2021",
                    location: "Lausanne, Switzerland",
                    description: "- Minor in Management, Technology & Entrepreneurship.\n" +
                        "- Semester 1 : Machine Learning, Applied Data Analysis, Natural Language Processing, Principle of Finance, Microeconomics, Project Management & Risk Analysis."

                },
                {
                    link:"https://www.ust.hk",
                    img_src: "/pierre-website_education_2.png",
                    title: "Exchange Program, Computer Science",
                    company: "Hong Kong University of Science And Technology",
                    date: "September 2018 - June 2019",
                    location: "Hong Kong, China",
                    description: "- Exchange program during the 3rd year of EPFL bachelor's program.\n" +
                        "- Research Project: Develop a decentralized file-sharing application using Ethereum blockchain technology, with Dr.Chatzopoulos (supervision of Pr. Hui). Collaborate as the first author on an ongoing research paper.\n" +
                        "- Relevant Courses: Computer and Network Security, Database Management Systems, Signal Processing, Digital Communications, Machine Learning, Stochastic Modeling."

                },

                {
                    link:"https://epfl.ch",
                    img_src: "/pierre-website_education_1.png",
                    title: "Bachelor of Science in Communication Systems",
                    company: "Swiss Federal Institute of Technology (EPFL)",
                    date: "September 2016 - August 2019",
                    location: "Lausanne, Switzerland",
                    description: "- Selected amongst 4% of first-year students to participate in the exchange\n" +
                        "program outside of Europe.\n" +
                        "- Built an Alps panorama drawer and a GameBoy console emulator in Java (Object Oriented Programming Course).\n" +
                        "- Relevant Courses: Computer Networks, Algorithms, Theory of Computation, Information Science, Object-Oriented Programming, Functional Programming, Computer Architecture, Discrete Math, Analysis, Algebra, Probabilities & Statistics."
                }
            ],

            leadership: [
        {
            link:"https://bsaepfl.ch",
            img_src: "/pierre-website_leadership_1.png",
            title: "Co-Founder, Vice-President",
            company: "Blockchain Student Association EPFL",
            date: "September 2019 - Present",
            location: "Lausanne, Switzerland",
            description: "- Co-found a student organization at EPFL that shares knowledge, issues, and develops projects in the field of distributed technologies for the university community.\n" +
                "- Build the administration structure of a new organisation\n" +
                "- Organize talks, workshops, hackathon and other events all along this year on EPFL campus.\n" +
                "- Manage the organization, the public relations for legal subjects."

        },
        {
            link:"https://coaching.epfl.ch",
            img_src: "/pierre-website_leadership_2.png",
            title: "Coach",
            company: "Coaching IC EPFL",
            date: "September 2017 - July 2018",
            location: "Lausanne, Switzerland",
            description: "- Provide moral and academic help to students during their first year at\n" +
                "university.\n" +
                "- Organize social events, weekend activities (skiing, attraction park, party, sport activities).\n" +
                "- Manage and give lectures during final examinations revisions to help students." + "- Manage the accounts of the organisation (banking, bills, ...).\n" +
                "- Design a yearly budget for activities and future development.\n" +
                "- Contact companies for sponsorship opportunities."

        },

    ],

            projects: [
                {
                    title: "DAppSter : Decentralized File Sharing System using Ethereum and BitTorrent",
                    img_src: "/pierre-website_project_5.png",
                    source_link:"https://github.com/stang-l/DAppSter",
                    keywords: "Java, Solidity, Ethereum, BitTorrent, Research, File sharing, Tracker",
                    description: "- This application has been realised during my exchange year in Hong Kong. \n" +
                        "- Develop a decentralized file sharing system that uses Ethereum blockchain to replace centralized trackers in BitTorrent protocol \n" +
                        "- Enables a more robust and decentralized bootstrapping and provide censorship resistant tracker. \n" +
                        "- Collaborate as the first author on an ongoing research paper."

                },
                {
                    title: "ECommerce Android Mobile Application",
                    img_src: "/pierre-website_project_3.png",
                    source_link:"https://github.com/pierreschutz/Firebase-Kotlin-Android-Simple-Read-Write",
                    description: "- This mobile application has been realised with the Junior Enterprise EPFL for a private company. \n" +
                        "- The application provides basic e-commerce application functions such as a cart, favorites, shop, etc. \n" +
                        "- The user is able to order from the application, schedule repair appointments, order customisable phone cases, etc. \n" +
                        "- Please find in source code an open-source component made to use Firebase real time database for appointment.",
                    keywords: "Kotlin, Mobile application, E-Commerce, Android, Junior Enterprise"

                },
                {
                    title: "Kaggle: TMDB Box Office prediction Competition",
                    img_src: "/pierre-website_project_7.png",
                    source_link:"https://github.com/pierreschutz/ML_HKUST",
                    description_link:"https://www.kaggle.com/c/tmdb-box-office-prediction",
                    keywords:"Python, Machine Learning, Pandas, SkLearn, Data Science",
                    description: "- This project has been realised during the Machine Learning course final project in Hong Kong. \n" +
                        "- The project contains the data analysis, data preprocessing, feature engineering and selection. \n" +
                        "- It also contains multiple trials with different machine learning methods in order to build a model with the best performances."

                },
                {
                    title: "Alpano: Alps panorama drawer",
                    img_src: "/pierre-website_project_1.png",
                    description_link:"https://cs108.epfl.ch/archive/17/p/00_introduction.html",
                    description: "- This application has been realised during the course of Oriented-Object Programming at EPFL (as a Student). \n" +
                        "- It consists of building a Alps panorama renderer from scratch in order to provide a landscape view of " +
                        "what you would see as well as the name of the summits visible when you provide GPS location in the Swiss Alps. ",
                    keywords: "Java, System Design, OOP, Drawer"

                },
                {
                    title: "Gameboj: Nintendo GameBoy Emulator",
                    img_src: "/pierre-website_project_2.png",
                    description_link:"https://cs108.epfl.ch/archive/18/p/00_introduction.html",
                    description: "- This application has been realised during the courses of Oriented-Object Programming at EPFL (as a Teaching Assistant). \n" +
                    "- It consists of building an Game Boy emulator reproducing virtually all the hardware of the original Game Boy. At the end, the program is able to read Cartridge designed for the Game Boy.",
                    keywords: "Java, System Design, OOP, Game"

                },
                {
                    title: "Blockchain Society Website",
                    img_src: "/pierre-website_project_4.png",
                    source_link:"",
                    description_link:"https://blockchainsociety.ch/",
                    description: "- Build the website of an organisation I am taking part during my free time (Blockchain Society). \n" +
                        "- Design and implement the stucture of the website on Wordpress.",
                    keywords: "Wordpress, Web"

                },

                {
                    title: "Pong Game Nios II Assembly",
                    img_src: "/pierre-website_project_6.png",
                    source_link:"https://github.com/pierreschutz/Pong-NiosII",
                    description_link: "https://gecko-wiki.ti.bfh.ch/geck4education_epfl:start",
                    keywords: "Assembly, Game, Nios II",
                    description: "- This application has been realised during my exchange year in Hong Kong. \n" +
                        "- Develop a decentralized file sharing system that uses Ethereum blockchain to replace centralized trackers in BitTorrent protocol \n" +
                        "- Enables a more robust and decentralized bootstrapping and provide censorship resistant tracker. \n" +
                        "- Collaborate as the first author on an ongoing research paper."

                },



            ],

        })
    }
    ;
</script>

<style scoped>
  .main-card {
    margin-top: 50px;
    margin-bottom: 50px;
    margin-left: 100px;
    margin-right: 100px;
  }
</style>
