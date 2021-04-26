<template>
  <v-layout column justify-center align-center>
    <v-flex xs12 sm8 md6>
      <!-- Picture, name and description -->
      <v-card class="main-card" color="rgba(0, 0, 0, 0.8)">
        <v-img class="my-img" height="400" src="/photo_berlin_pierre.jpg"></v-img>

        <v-card-title style="font-size: 2.5em">{{nameTitle}}</v-card-title>

        <v-card-text class="body-1">
          {{description}}
        </v-card-text>

        <v-card-actions>
          <v-btn href="https://linkedin.com/in/pierreschutz" target="_blank" outlined color="deep-purple" width="200">
            <v-icon>mdi-linkedin</v-icon>
            <v-label>LinkedIn</v-label>
          </v-btn>
          <v-btn href="https://github.com/pierreschutz" target="_blank" outlined color="deep-purple" width="200">
            <v-icon>mdi-github</v-icon>
            <v-label>GitHub</v-label>
          </v-btn>
          <v-btn href="mailto:pierreschutz@rocketmail.com" target="_blank" outlined color="deep-purple" width="200">
            <v-icon>mdi-email-box</v-icon>
            <v-label>EMail</v-label>
          </v-btn>


        </v-card-actions>
      </v-card>

      <!-- Resume Section -->
      <v-expansion-panels v-model="resumePanels" multiple style="margin: 100px 0">
        <h1 style="font-weight: bold">My Resume</h1>
        <!-- Experience block -->
        <v-expansion-panel class="resume-panel">

          <v-expansion-panel-header>
            <h2 style="font-weight: bold">Experience</h2>
          </v-expansion-panel-header>

          <v-expansion-panel-content>
            <resume-item

              v-for="item in experience"
              v-bind:key="item.title"
              :link="item.link"
              :color="item.color"
              :img_src="item.img_src"
              :title="item.title"
              :description="item.description"
              :company="item.company"
              :date="item.date"
              :location="item.location"

            ></resume-item>

          </v-expansion-panel-content>

        </v-expansion-panel>
        <!-- Education block -->
        <v-expansion-panel class="resume-panel" >

          <v-expansion-panel-header>
            <h2 style="font-weight: bold">Education</h2>
          </v-expansion-panel-header>

          <v-expansion-panel-content>
            <resume-item

              v-for="item in education"
              v-bind:key="item.title"
              :color="item.color"
              :link="item.link"
              :img_src="item.img_src"
              :title="item.title"
              :description="item.description"
              :company="item.company"
              :date="item.date"
              :location="item.location"

            ></resume-item>
          </v-expansion-panel-content>

        </v-expansion-panel>

        <!-- Leadership activities -->

        <v-expansion-panel class="resume-panel" >

          <v-expansion-panel-header>
            <h2 style="font-weight: bold">Leadership Activities</h2>
          </v-expansion-panel-header>

          <v-expansion-panel-content>

            <resume-item

              v-for="item in leadership"
              v-bind:key="item.title"
              :color="item.color"
              :link="item.link"
              :img_src="item.img_src"
              :title="item.title"
              :description="item.description"
              :company="item.company"
              :date="item.date"
              :location="item.location"

            ></resume-item>

          </v-expansion-panel-content>

        </v-expansion-panel>

        <!-- Software Projects -->

        <v-expansion-panel class="resume-panel" >

          <v-expansion-panel-header>
            <h2 style="font-weight: bold">Software Projects</h2>
          </v-expansion-panel-header>

          <v-expansion-panel-content>
            <project-item

              v-for="item in projects"
              v-bind:key="item.title"
              :color="item.color"
              :source_link="item.source_link"
              :description_link="item.description_link"
              :project_link="item.project_link"
              :report_link="item.report_link"
              :img_src="item.img_src"
              :date="item.date"
              :title="item.title"
              :description="item.description"
              :keywords="item.keywords"

            ></project-item>

          </v-expansion-panel-content>

        </v-expansion-panel>

      </v-expansion-panels>





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

      nameTitle: "Pierre Schutz",
      description:
        "Master Student in Data Science at EPFL (Swiss Federal Institute of Technology Lausanne).\n" +
        "          Vice-President and Treasurer of Blockchain Student Association at EPFL.\n" +
        "          Interested in Android mobile development, information security, decentralized systems, and Data Sciences.",
      resumePanels: [0, 1, 2, 3],
      experience: [
        {
          link: "https://amazon.com",
          title: "Software Engineer Intern",
          img_src: "/resume/amazon_icon.png",
          company: "Amazon",
          date: "October 2020 - February 2021",
          location: "Kirchberg, Luxembourg"
        },
        {
          link: "https://inpher.io",
          img_src: "/resume/inpher_icon.png",
          title: "Software Developer",
          company: "Inpher",
          date: "Intern (June 2019 - August 2019), Part-Time (October 2019 - July 2020)",
          location: "New York, USA / Lausanne, Switzerland",
          description: "- Build a configuration's files manager interface that helps clients to create, read, edit and delete configurations file on their machine (Using Vue.js, Javascript, Node.js, Docker).\n" +
            "- Acquire working knowledge about secret computing and privacy-preserving machine learning."

        },
        {
          link: "https://je.epfl.ch",
          img_src: "/resume/je_epfl_icon.png",
          title: "Technical Consultant, Software Developer",
          company: "Junior Enterprise EPFL",
          date: "March 2018 - February 2020",
          location: "Lausanne, Switzerland",
          description: "- Consult on IT projects about databases, publish-subscribe pattern\n" +
            "systems, mobile applications, e-commerce applications, SDK, web API.\n" +

            "- Design specifications and time estimations for mobile or web development projects.\n" +

            "- Test and analyze the behavior of mobile applications, and mobile frameworks (Matchmore.io).\n" +

            "- Design and develop Android applications in Kotlin."

        },

        {
          link: "https://epfl.ch",
          img_src: "/resume/epfl_icon.png",
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
          img_src: "/resume/epfl_icon.png",
          title: "Master of Science, Data Science",
          company: "Swiss Federal Institute of Technology (EPFL)",
          date: "September 2019 - March 2022",
          location: "Lausanne, Switzerland",
          description: "- Minor in Management, Technology & Entrepreneurship.\n" +
            "- Semester 1 : Machine Learning, Applied Data Analysis, Natural Language Processing, Principle of Finance, Microeconomics, Project Management & Risk Analysis."

        },
        {
          link: "https://hkust.edu.hk/",
          img_src: "/resume/hkust_icon.png",
          title: "Exchange Program, Computer Science",
          company: "Hong Kong University of Science And Technology",
          date: "September 2018 - June 2019",
          location: "Hong Kong, China",
          description: "- Exchange program during the 3rd year of EPFL bachelor's program.\n" +
            "- Research Project: Develop a decentralized file-sharing application using Ethereum blockchain technology, with Dr.Chatzopoulos (supervision of Pr. Hui). Collaborate as the first author on an ongoing research paper.\n" +
            "- Relevant Courses: Computer and Network Security, Database Management Systems, Signal Processing, Digital Communications, Machine Learning, Stochastic Modeling."

        },

        {
          link: "https://epfl.ch",
          img_src: "/resume/epfl_icon.png",
          title: "Bachelor of Science, Communication Systems",
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
          link: "https://bsaepfl.ch",
          img_src: "/resume/bsa_icon.png",
          title: "Co-Founder",
          company: "Blockchain Student Association EPFL",
          date: "September 2018 - October 2020",
          location: "Lausanne, Switzerland",
          description: "- Co-found a student organization at EPFL that shares knowledge, issues, and develops projects in the field of distributed technologies for the university community.\n" +
            "- Build the administration structure of a new organisation\n" +
            "- Organize talks, workshops, hackathon and other events all along this year on EPFL campus.\n" +
            "- Manage the organization, the public relations for legal subjects."

        },
        {
          link: "https://coaching.epfl.ch",
          img_src: "/resume/coaching_icon.png",
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
          title: "World Map Visualisation",
          date: "2021",
          img_src: "/resume/world_map_icon.png",
          project_link: "/map",
          keywords: "Javascript, D3, Web",
          description: "Fun personal project to train using d3.js. Built an interactive world map visualisation."
        },
        {
          title: "Chicago Crime Data visualisation",
          date: "2020",
          img_src: "/resume/chicago_crime_icon.png",
          project_link: "https://pierreschutz.github.io/dada-story",
          source_link: "https://github.com/pierreschutz/ADA_Project/",
          keywords: "Data Analysis, Web, Chicago crime, Python, Machine Learning, EPFL, Team work",
          description: "Group work for the Applied Data Analysis course. " +
            "Analysis of the kaggle's dataset containing 20 years of crime in Chicago. " +
            "Data preprocessing, analysis, and visual presentation in a data story. "
        },
        {
          title: "DAppSter : Decentralized File Sharing System using Ethereum and BitTorrent",
          date: "2019",
          img_src: "/resume/dappster_icon.png",
          source_link: "https://github.com/stang-l/DAppSter",
          keywords: "Java, Solidity, Ethereum, BitTorrent, Research, File sharing, Tracker",
          description: "- Decentralized file sharing system that uses Ethereum blockchain to replace centralized trackers in BitTorrent protocol \n" +
            "- Enables a more robust and decentralized bootstrapping and provide censorship resistant tracker. \n" +
            "- Collaborate as the first author on an ongoing research paper."

        },
        {
          title: "Kaggle: TMDB Box Office prediction Competition",
          date: "2019",
          img_src: "/resume/boxoffice_icon.png",
          source_link: "https://github.com/pierreschutz/ML_HKUST",
          description_link: "https://www.kaggle.com/c/tmdb-box-office-prediction",
          keywords: "Python, Machine Learning, Pandas, SkLearn, Data Science",
          description: "- This project has been realised during the Machine Learning course final project in Hong Kong. \n" +
            "- The project contains the data analysis, data preprocessing, feature engineering and selection. \n" +
            "- It also contains multiple trials with different machine learning methods in order to build a model with the best performances."

        },
        {
          title: "Gameboj: Nintendo GameBoy Emulator",
          date: "2018",
          img_src: "/resume/gameboy_icon.png",
          description_link: "https://cs108.epfl.ch/archive/18/p/00_introduction.html",
          description: "- This application has been realised during the courses of Oriented-Object Programming at EPFL (as a Teaching Assistant). \n" +
            "- It consists of building an Game Boy emulator reproducing virtually all the hardware of the original Game Boy. At the end, the program is able to read Cartridge designed for the Game Boy.",
          keywords: "Java, System Design, OOP, Game"

        },
        {
          title: "Pong Game Nios II Assembly",
          date: "2018",
          img_src: "/resume/pong_icon.png",
          source_link: "https://github.com/pierreschutz/Pong-NiosII",
          description_link: "https://gecko-wiki.ti.bfh.ch/geck4education_epfl:start",
          keywords: "Assembly, Game, Nios II",
          description: "- This application has been realised during my exchange year in Hong Kong. \n" +
            "- Develop a decentralized file sharing system that uses Ethereum blockchain to replace centralized trackers in BitTorrent protocol \n" +
            "- Enables a more robust and decentralized bootstrapping and provide censorship resistant tracker. \n" +
            "- Collaborate as the first author on an ongoing research paper."

        },
        {
          title: "Alpano: Alps panorama drawer",
          date: "2017",
          img_src: "/resume/alpano_icon.png",
          description_link: "https://cs108.epfl.ch/archive/17/p/00_introduction.html",
          description: "- This application has been realised during the course of Oriented-Object Programming at EPFL (as a Student). \n" +
            "- It consists of building a Alps panorama renderer from scratch in order to provide a landscape view of " +
            "what you would see as well as the name of the summits visible when you provide GPS location in the Swiss Alps. ",
          keywords: "Java, System Design, OOP, Drawer"
        },
      ],

    }),
  }
  ;
</script>

<style scoped>
  .main-card {
    margin: 50px 100px;
  }

  .my-img {
    border-radius: 10px;
  }

  .resume-panel {
    background: rgba(0, 0, 0, 0.2)!important;
  }

</style>
