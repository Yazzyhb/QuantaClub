<template>
  <!-- ======= Top Bar ======= -->
<div id="topbar" class="d-flex align-items-center fixed-top">
  <div class="container d-flex justify-content-between">
    <div class="contact-info d-flex align-items-center">
      <i class="bi bi-envelope"></i> <a href="mailto:quantaclubdz@gmail.com">quantaclubdz@gmail.com</a>
      <i class="bi bi-phone"></i> {{ phoneNumber }}
    </div>
    <div class="d-none d-lg-flex social-links align-items-center">
      <a href="https://github.com/quantaclubdz" class="github"><i class='bx bxl-github'></i></a>
      <a href="https://www.facebook.com/quantaclubdz" class="facebook"><i class='bx bxl-facebook'></i></a>
      <a href="https://www.instagram.com/quanta_club/" class="instagram"><i class='bx bxl-instagram'></i></a>
      <a href="https://www.linkedin.com/company/quantaclubdz/" class="linkedin"><i class='bx bxl-linkedin'></i></a>
    </div>
  </div>
</div>



  <!-- ======= Header ======= -->
  <header id="header" class="fixed-top">
    <div class="container d-flex align-items-center">
      <h1 class="logo me-auto"><router-link to="/"> 
        <img class="logo-image" src="@/assets/logoquanta.png" alt="Quanta Club Logo">
      </router-link></h1>

      <nav id="navbar" class="navbar order-last order-lg-0">
        <ul>
  <li>
    <button class="nav-button" @click="scrollToSection('events')">Events</button>
  </li>
  <li>
    <button class="nav-button" @click="scrollToSection('Departments')">Departments</button>
  </li>
  <li>
    <button class="nav-button" @click="scrollToSection('staff')">Staff</button>
  </li>
  <li>
    <button class="nav-button" @click="scrollToSection('contact')">Contact</button>
  </li>
        </ul>
        <!-- <i class="bi bi-list mobile-nav-toggle"></i> -->
      </nav>
      <router-link to="/#Membership" class="Membership-btn" @click.prevent="scrollToSection('Membership')">
  <span class="d-none d-md-inline">Become a</span> Member
</router-link>
    </div>
  </header><!-- End Header -->


    <!-- ======= Hero Section ======= -->
    <section id="hero" class="d-flex align-items-center">
    <div class="container">
      
    </div>
  </section><!-- End Hero -->




  <main id="main">

<!-- ======= Why Us Section ======= -->
<section id="why-us" class="why-us">
      <div class="container">

        <div class="row">
          <div class="col-lg-4 d-flex align-items-stretch">
            <div class="content">
              <h3>Why Choose Quanta Club?</h3>
              <p>
                Welcome to Quanta Club, where passion meets opportunity. Here are a few reasons why choosing us for your learning needs is the right decision.    
                        </p>
              <div class="text-center">
                <router-link to="#" class="more-btn" @click="scrollToSection('counts')">Learn More <i class="bx bx-chevron-right"></i></router-link>

              </div>
            </div>
          </div>
          <div class="col-lg-8 d-flex align-items-stretch">
            <div class="icon-boxes d-flex flex-column justify-content-center">
              <div class="row">
                <div class="col-xl-4 d-flex align-items-stretch">
                  <div class="icon-box mt-4 mt-xl-0">
                    <i class="fa-regular fa-lightbulb"></i>
                    <h4>Innovative Learning Environment</h4>
                    <p>
                      Engage in practical workshops and projects to develop real-world skills.
                    </p>
                  </div>
                </div>
                <div class="col-xl-4 d-flex align-items-stretch">
                  <div class="icon-box mt-4 mt-xl-0">
                    <i class="fa-solid fa-chalkboard-user"></i>
                  <h4>Expert Guidance and Mentorship</h4>
                    <p>Receive personalized support from experienced professionals and mentors.</p>
                  </div>
                </div>
                <div class="col-xl-4 d-flex align-items-stretch">
                  <div class="icon-box mt-4 mt-xl-0">
                    <i class="fa-solid fa-users-line"></i>
                      <h4>Collaborative Community</h4>
                    <p>Connect with passionate individuals and work on group projects.</p>
                  </div>
                </div>
              </div>
            </div><!-- End Departments content-->
          </div>
        </div>

      </div>
    </section><!-- End Why Us Section -->
      


  <!-- ======= Counts Section ======= -->
<section id="counts" class="counts">
  <div class="container">
    <div class="row justify-content-center">

      <div class="col-md-4" v-for="item in counterData" :key="item.trans">
        <div class="count-up">
          <div class="count-box">
            
            <i v-if="item.trans === 'Members'" class="fa-regular fa-user"></i>
      <i v-if="item.trans === 'Departments'" class="fas fa-building"></i>
      <i v-if="item.trans === 'Events'" class='fa-solid fa-award' ></i> 

            <h4>{{item.count}}</h4>
            <p>{{item.trans}}</p>
          </div>
        </div>
      </div>

    </div>
  </div>
</section>



<!-- ======= events Section ======= -->
<section id="events" class="events">
    <div class="container">
      <div class="section-title">
        <h2>Events</h2>
        <p>Explore the highlights of our recent events, from engaging workshops to vibrant social gatherings.</p>
      </div>
      <clubEvents :events="events" />
    </div>
  </section>
  <!-- End events Section -->




<!--Departments-->

<section id="Departments" class="Departments">
    <div class="container">

      <div class="section-title">
        <h2>Departments</h2>
        <p>Discover Our Club's Key Teams!</p>
      </div>

      <div class="row">
        <div class="col-lg-4 col-md-6 d-flex align-items-stretch" v-for="(department, index) in Departments" :key="index">
          <div class="icon-box">
            <div class="icon"><i :class="department.iconClass"></i></div>
            <h4><router-link :to="department.link">{{ department.title }}</router-link></h4>
            <p>{{ department.description }}</p>
          </div>
        </div>
      </div>

    </div>
  </section><!-- End dep Section -->



  <!-- form Section -->

  <section id="Membership" class="Membership section-bg">
    <div class="container">

      <div class="section-title">
        <h2>Become a Member</h2>
        <p>
          Join Our Club and Be Part of an Amazing Community!

Connect, learn, and grow with like-minded individuals. <br>

Please fill out the membership form below to become a part of our community
        </p>
      </div>

      <form @submit.prevent="submitForm" class="php-email-form">
        <div class="row">
          <div class="col-md-4 form-group">
            <input v-model="formData.name" type="text" required name="name" class="form-control" id="name" placeholder="Full Name" :data-rule="'minlen:4'" data-msg="Please enter at least 4 chars">
            <div class="validate"></div>
          </div>
          <div class="col-md-4 form-group mt-3 mt-md-0">
            <input v-model="formData.email" type="email" required class="form-control" name="email" id="email" placeholder="Email Address" :data-rule="'email'" data-msg="Please enter a valid email">
            <div class="validate"></div>
          </div>
          <div class="col-md-4 form-group mt-3 mt-md-0">
            <input v-model="formData.phone" type="tel" required class="form-control" name="phone" id="phone" placeholder="Phone Number" :data-rule="'minlen:4'" data-msg="Please enter at least 4 chars">
            <div class="validate"></div>
          </div>
        </div>

        
        <div class="row">
          
          <div class="col-md-4 form-group mt-3">
            <select v-model="formData.year" required name="year" id="year" class="form-select">
              <option value="">Year of Study</option>
              <option value=" Y1">First Year (L1)</option>
              <option value=" Y2">Second Year (L2)</option>
              <option value=" Y3">Third Year (L3)</option>
              <option value="Y4">Fourth Year (M1)</option>
              <option value="Y5">Fifth Year (M2)</option>

            </select>
            <div class="validate"></div>
          </div>
          <div class="col-md-4 form-group mt-3">
            <input v-model="formData.major" type="text"  name="major" class="form-control" id="major" placeholder="Major/Field of Study" :data-rule="'minlen:4'" data-msg="Please enter at least 4 chars">
            <div class="validate"></div>
          </div>


          <div class="col-md-4 form-group mt-3">
            <select v-model="formData.sm" name="sm" id="sm" class="form-select">
              <option value="">How did you hear about the club?</option>
              <option value=" 1">Social Media</option>
              <option value=" 2">Friend</option>
              <option value=" 3">University Event</option>
              <option value=" 4">Other</option>

            </select>
            <div class="validate"></div>
          </div>

      
          

        <div class="form-group mt-3">
          <textarea v-model="formData.message" class="form-control" name="message" required rows="5" placeholder="What skills or experiences can you bring to the club?"></textarea>
          <div class="validate"></div>
        </div>
        <div class="mb-3">
          <div class="loading" v-if="isLoading">Loading</div>
          <div class="error-message" v-if="errorMessage">{{ errorMessage }}</div>
          <div class="sent-message" v-if="successMessage">Your Membership request has been sent successfully. Thank you!</div>
        </div>

        <div class="text-center"> 

        <button class="butto" :disabled="isLoading">
          Become a Member
  <svg fill="currentColor" viewBox="0 0 24 24" class="icon">
    <path clip-rule="evenodd" d="M12 2.25c-5.385 0-9.75 4.365-9.75 9.75s4.365 9.75 9.75 9.75 9.75-4.365 9.75-9.75S17.385 2.25 12 2.25zm4.28 10.28a.75.75 0 000-1.06l-3-3a.75.75 0 10-1.06 1.06l1.72 1.72H8.25a.75.75 0 000 1.5h5.69l-1.72 1.72a.75.75 0 101.06 1.06l3-3z" fill-rule="evenodd"></path>
  </svg>
        </button>
        </div>
        </div>
      </form>

    </div>
    
  </section><!-- End form Section -->


<!-- ======= staff Section ======= -->
<section id="staff" class="staff">
    <div class="container">
      <div class="section-title">
        <h2>Meet Our Team</h2>
        <p>
          Our dedicated staff members are here to ensure a thriving community and provide the best experience for our club members.
        </p>
      </div>

      <div class="row">
  <div v-for="(teammember, index) in staff" :key="index" class="col-lg-6 mt-4">
    <div class="member d-flex align-items-start">
      <div class="pic"><img :src="teammember.image" class="img-fluid" alt="image"></div>
      <div class="member-info">
        <h4>{{ teammember.name }}</h4>
        <span>{{ teammember.specialization }}</span>
        <p>{{ teammember.description }}</p>
        <div class="social">
          <a :href="'#' + teammember.twitter"><i class='bx bxl-twitter'></i></a>
          <a :href="'#' + teammember.facebook"><i class='bx bxl-facebook' ></i></a>
          <a :href="'#' + teammember.instagram"><i class='bx bxl-instagram' ></i></a>
          <a :href="'#' + teammember.linkedin"><i class='bx bxl-linkedin' ></i></a>
        </div>
      </div>
    </div>
  </div>
</div>

    </div>
  </section><!-- End Staff Section -->

     <!-- ======= Frequently Asked Questions Section ======= -->
     <section id="faq" class="faq section-bg">
    <div class="container">
      <div class="section-title">
        <h2>Frequently Asked Questions</h2>
        <p>Find answers to common questions about our club, events, and membership. If you need more information, feel free to contact us.</p>
      </div>

      <div class="faq-list">
        <ul>
          <li v-for="(faq, index) in faqs" :key="index" data-aos="fade-up">
            <i class="bx bx-help-circle icon-help"></i>
            <a :data-bs-toggle="'collapse'" :data-bs-target="'#faq-list-' + (index + 1)"
               :class="{ 'collapsed': !faq.expanded, 'show': faq.expanded }"
               @click="toggleCollapse(index)">
              {{ faq.question }}
              <i class="bx" :class="[{ 'bx-chevron-down': !faq.expanded, 'bx-chevron-up': faq.expanded }, 'icon-show']"></i>
            </a>
            <div :id="'faq-list-' + (index + 1)" class="collapse" data-bs-parent=".faq-list">
              <p>{{ faq.answer }}</p>
            </div>
          </li>
        </ul>
      </div>
    </div>
  </section><!-- End Frequently Asked Questions Section -->



 <!-- ======= Contact Section ======= -->
 <section id="contact" class="contact">
    <div class="container">
      <div class="section-title">
        <h2>Contact</h2>
        <p>We value your feedback and inquiries. Reach out to us via phone or email. Our dedicated support team is here to assist you.</p>
      </div>
    </div>

    <div>
      <iframe style="border:0; width: 100%; height: 350px;" :src="googleMapsSrc" frameborder="0" allowfullscreen></iframe>
    </div>

    <div class="container">
      <div class="row mt-5">
        <div class="col-lg-4">
          <div class="info">
            <div class="address">
              <i class="bi bi-geo-alt"></i>
              <h4>Location:</h4>
              <p>{{ location }}</p>
            </div>

            <div class="email">
              <i class="bi bi-envelope"></i>
              <h4>Email:</h4>
              <p>{{ email }}</p>
            </div>

            <div class="phone">
              <i class="bi bi-phone"></i>
              <h4>Call:</h4>
              <p>{{ phoneNumber }}</p>
            </div>
          </div>
        </div>

        <div class="col-lg-8 mt-5 mt-lg-0">
          <form @submit.prevent="submitForm" class="php-email-form">
            <div class="row">
              <div class="col-md-6 form-group">
                <input v-model="formData.name" type="text" class="form-control" id="name" placeholder="Your Name" required>
              </div>
              <div class="col-md-6 form-group mt-3 mt-md-0">
                <input v-model="formData.email" type="email" class="form-control" id="email" placeholder="Your Email" required>
              </div>
            </div>
            <div class="form-group mt-3">
              <input v-model="formData.subject" type="text" class="form-control" id="subject" placeholder="Subject" required>
            </div>
            <div class="form-group mt-3">
              <textarea v-model="formData.message" class="form-control" rows="5" placeholder="Message" required></textarea>
            </div>
            <div class="my-3">
              <div class="loading" v-if="loading">Loading</div>
              <div class="error-message" v-if="errorMessage">{{ errorMessage }}</div>
              <div class="sent-message" v-if="successMessage">Your message has been sent. Thank you!</div>
            </div>
            <div class="text-center"><button type="submit">Send Message</button></div>
          </form>
        </div>
      </div>
    </div>
  </section><!-- End Contact Section -->

  </main>


  <!-- ======= Footer ======= -->
 <footer id="footer">
  

    <div class="container d-md-flex py-4">
      <div class="me-md-auto text-center text-md-start">
        <div class="copyright">
          &copy; Copyright <strong><span>QuantaClub</span></strong>. All Rights Reserved
        </div>
        <div class="credits">Designed by <strong> <span>QuantaClub</span></strong></div>
      </div>
      <div class="social-links text-center text-md-right pt-3 pt-md-0">
        <a href="https://github.com/quantaclubdz" class="github"><i class='bx bxl-github'></i></a>
      <a href="https://www.facebook.com/quantaclubdz" class="facebook"><i class='bx bxl-facebook'></i></a>
      <a href="https://www.instagram.com/quanta_club/" class="instagram"><i class='bx bxl-instagram'></i></a>
      <a href="https://www.linkedin.com/company/quantaclubdz/" class="linkedin"><i class='bx bxl-linkedin'></i></a>
      </div>
    </div>
  </footer>
<!-- End Footer -->

<div>
    <div id="preloader"></div>
    <a href="#" class="back-to-top d-flex align-items-center justify-content-center" @click="scrollToTop">
      <i class="bi bi-arrow-up-short"></i>
    </a>
  </div>

</template>

<script>

import 'bootstrap-icons/font/bootstrap-icons.css';
import 'boxicons/css/boxicons.min.css';
import '@fortawesome/fontawesome-free/css/all.css';
import 'swiper/css';
import 'swiper/css/navigation';
import 'swiper/css/pagination';

import Swiper from 'swiper';





import clubEvents from './clubEvents.vue';

export default {
  components: {
  clubEvents,
},
  data(){
    
    return{
      
      email: "quantaclubdz@gmail.com",
      phoneNumber: "+213 547298543",
      duration   : 300,
      googleMapsSrc: "https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3195.9971053302343!2d3.0553281!3d36.7706369!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x128fb258e74b7123%3A0xa31d6cb06299dd5b!2z2KzYp9mF2LnYqSDYqNmGINmK2YjYs9mBINio2YYg2K7Yr9ipIC0g2KfZhNis2LLYp9im2LE!5e0!3m2!1sar!2sdz!4v1722936009459!5m2!1sar!2sdz",
      location: " 02 avenue Didouche Mourad, Algeria. 16,000",
    
    counterData: [
      {
        trans: 'Members',
        id   : 150,
        count: 0,
        duration   : 30,
      },
      {
        trans: 'Departments',
        id   : 5,
        count: 0,
        duration   : 30,
      },
      {
        trans: 'Events',
        id   : 25,
        count: 0,
        duration   : 20,
      },
                ],
                
      Departments: [
        {
          iconClass: "fa-solid fa-people-group",
          title: "Human Resources",
          link: "#",
          description: "Oversees member recruitment, training, and development. Ensures a smooth administrative process and maintains a supportive environment.",
        },
        {
          iconClass: "fa-solid fa-photo-film",
          title: "Social Media",
          link: "#",
          description: "Curates and manages content across platforms to boost engagement, promote events, and enhance the club’s online presence.",
        },
        {
          iconClass: "fa-solid fa-microscope",
          title: "Scientific Activities",
          link: "#",
          description: "Organizes academic events and research initiatives. Aims to foster intellectual growth and offer members opportunities for scientific exploration.",
        },
        {
          iconClass: "fa-solid fa-handshake",
          title: "External and Internal Relations",
          link: "#",
          description: "Handles collaborations and communication with external partners and within the club. Focuses on strengthening relationships to expand the club’s reach and impact.",
        },
        {
          iconClass: "fa-solid fa-code",
          title: "Development Department ",
          link: "#",
          description: " Crafting and maintaining websites for events, developing platforms for club activities , and contributing to open source initiatives. Projects : AI, mobile apps, web development...",
        },
        // {
        //   iconClass: "fas fa-notes-medical",
        //   title: "Mental Health and Wellness",
        //   link: "#",
        //   description: "Prioritize your well-being with our dedicated Mental Health and Wellness team. We offer counseling, therapy, and assessments to support emotional resilience and a balanced lifestyle. Your mental health is crucial to your overall well-being, and we're here for you.",
        // },
      ],
      
    staff: [
        {
          name: "Ayoub Sarri",
          specialization: "President",
          description: " As our President, Ayoub Sarri brings extensive leadership experience and a strong vision for the club’s future.",
          twitter: "Ayoub_twitter",
          facebook: "Ayoub_facebook",
          instagram: "Ayoub_instagram",
          linkedin: "Ayoub_linkedin",
          // image: require('@/assets/.jpg'),
        },
        {
          name: "Wissem",
          specialization: "Vice President",
          description: " Wissem, our Vice President, supports the President in managing the club’s activities and operations.",
          twitter: "Wissem_twitter",
          facebook: "Wissem_facebook",
          instagram: "Wissem_instagram",
          linkedin: "Wissem_linkedin",
          // image: require('@/assets/.jpg'),
        },
        {
          name: "Shaima",
          specialization: "HR Team Lead",
          description: "Shaima, our HR Team Lead, focuses on member recruitment and relations, bringing expertise in creating a welcoming and supportive environment for all club members. ",
          twitter: "Shaima_twitter",
          facebook: "Shaima_facebook",
          instagram: "Shaima_instagram",
          linkedin: "Shaima_linkedin",
          // image: require('@/assets/.jpg'),
        },
        {
          name: "Amel Soltani",
          specialization: "Activities Team Lead",
          description: "As our Activities Team Lead, Amel Soltani excels in planning and coordinating engaging events and activities, ensuring well-organized and memorable experiences for the club.",
          twitter: "Amel_twitter",
          facebook: "Amel_facebook",
          instagram: "Amel_instagram",
          linkedin: "Amel_linkedin",
          // image: require('@/assets/.jpg'),
        },
      ],
      faqs: [
        {
          question: "What is the purpose of the club?",
          answer: "Our club aims to foster a supportive community where members can connect, learn, and grow. We organize events, workshops, and activities to enhance personal and professional development.",
          expanded: true,
        },
        {
          question: "How can I become a member?",
          answer: "To join our club, simply fill out the membership form available on our website. Once submitted, you’ll receive a confirmation email with further details on the next steps.",
          expanded: false,
        },
        {
          question: "What types of events does the club organize?",
          answer: "We host a variety of events, including workshops, seminars, social gatherings, and community outreach programs. Our Activities Team Lead coordinates these events to ensure they are engaging and relevant to our members.",
          expanded: false,
        },
        {
          question: " Can I suggest new ideas or activities for the club?",
          answer: "Absolutely! We encourage members to share their ideas and suggestions. You can submit your ideas through our website’s contact form or bring them up during our meetings.",
          expanded: false,
        },
      ],
      
      formData: {
        name: '',
        email: '',
        phone: '',
        year: '',
      
        sm: '',
        major:'',
        message: '',
      },
      isLoading: false,
      errorMessage: '',
      successMessage: '',
    }
  },
  mounted() {
      this.showStep();

    new Swiper('.events-slider', {
      speed: 600,
      loop: true,
      autoplay: {
        delay: 5000,
        disableOnInteraction: false,
      },
      slidesPerView: 'auto',
      pagination: {
        el: '.swiper-pagination',
        type: 'bullets',
        clickable: true,
    
      },
      breakpoints: {
        320: {
          slidesPerView: 1,
          spaceBetween: 20,
        },
        1200: {
          slidesPerView: 2,
          spaceBetween: 20,
        },
      },  
      });
      
  },
  methods: {
    //ap
    
    selectCategory(category) {
        this.selectedCategory = category;
        this.nextStep();
      },
      selectMedicalDetail(detail) {
        this.selectedMedicalDetail = detail;
        this.nextStep();
      },
      selectDetailPart2(option) {
        this.selectedDetailPart2 = option;
        this.nextStep();
      },
      confirmDemande() {
        // Add your logic to handle confirmation
        // This is where you can proceed to the next step or submit the form
        // For now, let's just go to the next step
        this.nextStep();
      },
      selectSchedule(schedule) {
        this.selectedSchedule = schedule;
        this.nextStep();
      },
      nextStep() {
        this.currentStep++;
        this.showStep();
      },
      prevStep() {
        this.currentStep--;
        this.showStep();
      },
      showStep() {
        const steps = document.querySelectorAll('.form-step');
        steps.forEach((step, index) => {
          step.style.display = index + 1 === this.currentStep ? 'block' : 'none';
        });
      },
    //ap
    toggleCollapse(index) {
      this.faqs.forEach((faq, i) => {
        faq.expanded = i === index ? !faq.expanded : false;
      });
    },
    scrollToSection(sectionId) {
      const section = document.getElementById(sectionId);
      if (section) {
        section.scrollIntoView({ behavior: 'smooth' });
      }
    },
    scrollToTop() {
      // Add logic to scroll to the top of the page
      window.scrollTo({ top: 0, behavior: 'smooth' });
    },
    submitForm() {
      // Add your form submission logic here

      this.isLoading = true;

      // Simulate an API request with a delay
      setTimeout(() => {
        // Reset loading state and show success message
        this.isLoading = false;
        this.successMessage = 'Your Membership request has been sent successfully. Thank you!';
      
      }, 2000);
    },
  },
  created() {
    this.counterData.forEach((item) => {
      setInterval(() => {
        if (item.count < item.id) {
          item.count++;
        }
      }, item.duration);
    });
    
    },
   
    
}
</script>

<style >
body {
  font-family: "Open Sans", sans-serif;
  color: #444444;
}

a {
  color: #1977cc;
  text-decoration: none;
}

a:hover {
  color: #3291e6;
  text-decoration: none;
}

h1,
h2,
h3,
h4,
h5,
h6 {
  font-family: "Raleway", sans-serif;
}







/*--------------------------------------------------------------
# Top Bar
--------------------------------------------------------------*/
#topbar {
  background: #fff;
  height: 40px;
  font-size: 14px;
  transition: all 0.5s;
  z-index: 996;
}

#topbar.topbar-scrolled {
  top: -40px;
}

#topbar .contact-info a {
  line-height: 1;
  color: #444444;
  transition: 0.3s;
}

#topbar .contact-info a:hover {
  color: #1977cc;
}

#topbar .contact-info i {
  color: #1977cc;
  padding-right: 4px;
  margin-left: 15px;
  line-height: 0;
}

#topbar .contact-info i:first-child {
  margin-left: 0;
}

#topbar .social-links a {
  color: #437099;
  padding-left: 15px;
  display: inline-block;
  line-height: 1px;
  transition: 0.3s;
}

#topbar .social-links a:hover {
  color: #1977cc;
}

#topbar .social-links a:first-child {
  border-left: 0;
}

.scrolled #topbar {
  top: -40px;
}

/*--------------------------------------------------------------
# Header
--------------------------------------------------------------*/
#header {
  background: rgba(255, 255, 255, 255); 
  transition: all 0.5s;
  z-index: 997;
  /* padding: 5px 0; */
  top: 40px;
 box-shadow: 0px 2px 15px rgba(25, 119, 204, 0.1);
}


.logo-image {
  width: 100px; 
  height: auto; 
}

#header .container {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

#header .logo {
  font-size: 30px;
  margin: 0;
  padding: 0;
  line-height: 1;
  font-weight: 700;
  letter-spacing: 0.5px;
  font-family: "Poppins", sans-serif;
}

#header .logo a {
  color: #2c4964;
}

#navbar ul {
  list-style: none;
  display: flex;
  margin: 0;
  padding: 0;
  align-items: center;

}

#navbar ul li {
  margin-right: 20px;
}

#navbar .nav-link {
  color: #2c4964;
  text-decoration: none;
  font-size: 16px;
}

#navbar .nav-link:hover {
  color: #1977cc;
}
#navbar a i,
#navbar a:focus i {
  font-size: 12px;
  line-height: 0;
  margin-left: 5px;
  border-bottom: 2px solid #fff;

}
.Membership-btn {
  background-color: #1977cc;
  color: #fff;
  padding: 10px 20px;
  border-radius: 20px;
  text-decoration: none;
  font-weight: bold;
  margin-left: 25px;
  cursor: pointer;
  white-space: nowrap;
  transition: 0.3s;
  font-size: 14px;
  display: inline-block;
  letter-spacing: 1px;


}

.Membership-btn:hover {
  background-color: #3291e6;
  color: #fff;

}
@media (max-width: 768px) {
  .Membership-btn {
    margin: 0 15px 0 0;
    padding: 6px 18px;
  }
}
.nav-button {
  background-color: #ffffff; /* Set your desired background color */
  /* color: #e5eaf2; Set your desired text color */
  border: none;
  padding: 10px 20px;
  border-radius: 5px;
  cursor: pointer;
}
.nav-button:hover {
  color: #3291e6;}
  
/*--------------------------------------------------------------
# Hero Section
--------------------------------------------------------------*/

  #hero {
  width: 100%;
  height: 100vh;
  margin-bottom: -200px;
  background: url('@/assets/Quantabg.jpg') right center no-repeat;
  background-size: contain;
}


#hero .container {
  position: relative;
}

#hero h1 {
  margin: 0;
  font-size: 48px;
  font-weight: 700;
  line-height: 56px;
  text-transform: uppercase;
  color: #2c4964;
  margin-left: -600px;

}

#hero h2 {
  color: #2c4964;
  margin: 10px 0 0 0;
  font-size: 24px;
margin-left: -600px;
}

#hero .btn-get-started {
  /* font-family: "Raleway", sans-serif; */
  text-transform: uppercase;
  font-weight: bold;
  font-size: 14px;
  letter-spacing: 1px;
  display: inline-block;
  padding: 12px 35px;
  margin-top: 30px;
  border-radius: 50px;
  transition: 0.5s;
  color: #fff;
  background: #1977cc;
  margin-left: -600px;
  border: none;

}

#hero .btn-get-started:hover {
  background: #3291e6;
}

@media (min-width: 1024px) {
  #hero {
    background-attachment: fixed;
  }
}

@media (max-width: 992px) {
  #hero {
    margin-bottom: 0;
    height: 100vh;
  }

  #hero .container {
    padding-bottom: 63px;
  }

  #hero h1 {
    font-size: 28px;
    line-height: 36px;
  }

  #hero h2 {
    font-size: 18px;
    line-height: 24px;
    margin-bottom: 30px;
  }
}

@media (max-height: 600px) {
  #hero {
    height: 110vh;
  }
}


/*--------------------------------------------------------------
# Sections General
--------------------------------------------------------------*/
section {
  padding: 60px 0;
  overflow: hidden;
}

.section-bg {
  background-color: #f1f7fd;
}

.section-title {
  text-align: center;
  padding-bottom: 30px;
}

.section-title h2 {
  font-size: 32px;
  font-weight: bold;
  margin-bottom: 20px;
  padding-bottom: 20px;
  position: relative;
  color: #2c4964;
}

.section-title h2::before {
  content: "";
  position: absolute;
  display: block;
  width: 120px;
  height: 1px;
  background: #ddd;
  bottom: 1px;
  left: calc(50% - 60px);
}

.section-title h2::after {
  content: "";
  position: absolute;
  display: block;
  width: 40px;
  height: 3px;
  background: #1977cc;
  bottom: 0;
  left: calc(50% - 20px);
}

.section-title p {
  margin-bottom: 0;
}

/*--------------------------------------------------------------
# Breadcrumbs
--------------------------------------------------------------*/
.breadcrumbs {
  padding: 20px 0;
  background-color: #f1f7fd;
  min-height: 40px;
  margin-top: 120px;
}

@media (max-width: 992px) {
  .breadcrumbs {
    margin-top: 100px;
  }
}

.breadcrumbs h2 {
  font-size: 24px;
  font-weight: 300;
  margin: 0;
}

@media (max-width: 992px) {
  .breadcrumbs h2 {
    margin: 0 0 10px 0;
  }
}

.breadcrumbs ol {
  display: flex;
  flex-wrap: wrap;
  list-style: none;
  padding: 0;
  margin: 0;
  font-size: 14px;
}

.breadcrumbs ol li+li {
  padding-left: 10px;
}

.breadcrumbs ol li+li::before {
  display: inline-block;
  padding-right: 10px;
  color: #6c757d;
  content: "/";
}

@media (max-width: 768px) {
  .breadcrumbs .d-flex {
    display: block !important;
  }

  .breadcrumbs ol {
    display: block;
  }

  .breadcrumbs ol li {
    display: inline-block;
  }
}

/*--------------------------------------------------------------
# Why Us
--------------------------------------------------------------*/
.why-us .content {
  padding: 70px;
  background: #1977cc;
  border-radius: 4px;
  color: #fff;
}

.why-us .content h3 {
  font-weight: 700;
  font-size: 34px;
  margin-bottom: 30px;
}

.why-us .content p {
  margin-bottom: 30px;
}

.why-us .content .more-btn {
  display: inline-block;
  background: rgba(255, 255, 255, 0.2);
  padding: 6px 30px 8px 30px;
  color: #fff;
  border-radius: 50px;
  transition: all ease-in-out 0.4s;
}

.why-us .content .more-btn i {
  font-size: 14px;
}

.why-us .content .more-btn:hover {
  color: #1977cc;
  background: #fff;
}

.why-us .icon-boxes .icon-box {
  text-align: center;
  border-radius: 10px;
  background: #fff;
  box-shadow: 0px 2px 15px rgba(0, 0, 0, 0.1);
  padding: 40px 30px;
  width: 100%;
}

.why-us .icon-boxes .icon-box i {
  font-size: 40px;
  color: #1977cc;
  margin-bottom: 30px;
}

.why-us .icon-boxes .icon-box h4 {
  font-size: 20px;
  font-weight: 700;
  margin: 0 0 30px 0;
}

.why-us .icon-boxes .icon-box p {
  font-size: 15px;
  color: #848484;
}

/*--------------------------------------------------------------
# About
--------------------------------------------------------------*/
.about .icon-boxes h4 {
  font-size: 18px;
  color: #4b7dab;
  margin-bottom: 15px;
}

.about .icon-boxes h3 {
  font-size: 28px;
  font-weight: 700;
  color: #2c4964;
  margin-bottom: 15px;
}

.about .icon-box {
  margin-top: 40px;
}

.about .icon-box .icon {
  float: left;
  display: flex;
  align-items: center;
  justify-content: center;
  width: 64px;
  height: 64px;
  border: 2px solid #8dc2f1;
  border-radius: 50px;
  transition: 0.5s;
}

.about .icon-box .icon i {
  color: #1977cc;
  font-size: 32px;
}

.about .icon-box:hover .icon {
  background: #1977cc;
  border-color: #1977cc;
}

.about .icon-box:hover .icon i {
  color: #fff;
}

.about .icon-box .title {
  margin-left: 85px;
  font-weight: 700;
  margin-bottom: 10px;
  font-size: 18px;
}

.about .icon-box .title a {
  color: #343a40;
  transition: 0.3s;
}

.about .icon-box .title a:hover {
  color: #1977cc;
}

.about .icon-box .description {
  margin-left: 85px;
  line-height: 24px;
  font-size: 14px;
}

.about .video-box {
  background: url('@/assets/about.jpg');
  background-size: cover;
  min-height: 500px;
}

.about .play-btn {
  width: 94px;
  height: 94px;
  background: radial-gradient(#1977cc 50%, rgba(25, 119, 204, 0.4) 52%);
  border-radius: 50%;
  display: block;
  position: absolute;
  left: calc(50% - 47px);
  top: calc(50% - 47px);
  overflow: hidden;
}

.about .play-btn::after {
  content: "";
  position: absolute;
  left: 50%;
  top: 50%;
  transform: translateX(-40%) translateY(-50%);
  width: 0;
  height: 0;
  border-top: 10px solid transparent;
  border-bottom: 10px solid transparent;
  border-left: 15px solid #fff;
  z-index: 100;
  transition: all 400ms cubic-bezier(0.55, 0.055, 0.675, 0.19);
}

.about .play-btn::before {
  content: "";
  position: absolute;
  width: 120px;
  height: 120px;
  animation-delay: 0s;
  animation: pulsate-btn 2s;
  animation-direction: forwards;
  animation-iteration-count: infinite;
  animation-timing-function: steps;
  opacity: 1;
  border-radius: 50%;
  border: 5px solid rgba(25, 119, 204, 0.7);
  top: -15%;
  left: -15%;
  background: rgba(198, 16, 0, 0);
}

.about .play-btn:hover::after {
  border-left: 15px solid #1977cc;
  transform: scale(20);
}

.about .play-btn:hover::before {
  content: "";
  position: absolute;
  left: 50%;
  top: 50%;
  transform: translateX(-40%) translateY(-50%);
  width: 0;
  height: 0;
  border: none;
  border-top: 10px solid transparent;
  border-bottom: 10px solid transparent;
  border-left: 15px solid #fff;
  z-index: 200;
  animation: none;
  border-radius: 0;
}

@keyframes pulsate-btn {
  0% {
    transform: scale(0.6, 0.6);
    opacity: 1;
  }

  100% {
    transform: scale(1, 1);
    opacity: 0;
  }
}

/*--------------------------------------------------------------
# Counts
--------------------------------------------------------------*/

#counts {
  background: #f1f7fd;
  padding: 60px 0;
}

.counts .count-up {
  text-align: center;
  padding: 30px;
  width: 100%;
  position: relative;
  background: #fff;
  border-radius: 10px;
  margin-bottom: 20px;
  box-shadow: 0px 0px 20px rgba(0, 0, 0, 0.1);
}

.counts .count-up span {
  font-size: 36px;
  display: block;
  font-weight: 600;
  color: #1977cc; /* Change the color to match the theme */
}

.counts .count-up p {
  margin-top: 20px;
  font-size: 18px;
  color: #555;
}

.counts .count-box {
  text-align: center;
}

.counts .count-box i {
  font-size: 36px;
  color: #1977cc; /* Change the color to match the theme */
}

.counts .count-box h4 {
  font-size: 20px;
  font-weight: 700;
  margin: 15px 0;
  color: #2c4964; /* Change the color to match the theme */
}


/*--------------------------------------------------------------
# Departments
--------------------------------------------------------------*/
.Departments .icon-box {
  text-align: center;
  border: 1px solid #d5e1ed;
  padding: 80px 20px;
  transition: all ease-in-out 0.3s;
}

.Departments .icon-box .icon {
  margin: 0 auto;
  width: 64px;
  height: 64px;
  background: #1977cc;
  border-radius: 5px;
  transition: all 0.3s ease-out 0s;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 20px;
  transform-style: preserve-3d;
  position: relative;
  z-index: 2;
}

.Departments .icon-box .icon i {
  color: #fff;
  font-size: 28px;
  transition: ease-in-out 0.3s;
}

.Departments .icon-box .icon::before {
  position: absolute;
  content: "";
  left: -8px;
  top: -8px;
  height: 100%;
  width: 100%;
  background: rgba(25, 119, 204, 0.2);
  border-radius: 5px;
  transition: all 0.3s ease-out 0s;
  transform: translateZ(-1px);
  z-index: -1;
}

.Departments .icon-box h4 {
  font-weight: 700;
  margin-bottom: 15px;
  font-size: 24px;
}

.Departments .icon-box h4 a {
  color: #2c4964;
}

.Departments .icon-box p {
  line-height: 24px;
  font-size: 14px;
  margin-bottom: 0;
}

.Departments .icon-box:hover {
  background: #1977cc;
  border-color: #1977cc;
}

.Departments .icon-box:hover .icon {
  background: #fff;
}

.Departments .icon-box:hover .icon i {
  color: #1977cc;
}

.Departments .icon-box:hover .icon::before {
  background: rgba(255, 255, 255, 0.3);
}

.Departments .icon-box:hover h4 a,
.Departments .icon-box:hover p {
  color: #fff;
}
/*--------------------------------------------------------------
# Memberships
--------------------------------------------------------------*/
 /* .Membership .php-email-form {
  width: 100%;
}

.Membership .php-email-form .form-group {
  padding-bottom: 8px;
}

.Membership .php-email-form .validate {
  display: none;
  color: red;
  margin: 0 0 15px 0;
  font-weight: 400;
  font-size: 13px;
}

.Membership .php-email-form .error-message {
  display: none;
  color: #fff;
  background: #ed3c0d;
  text-align: left;
  padding: 15px;
  font-weight: 600;
}

.Membership .php-email-form .error-message br+br {
  margin-top: 25px;
}

.Membership .php-email-form .loading:before {
  content: "";
  display: inline-block;
  border-radius: 50%;
  width: 24px;
  height: 24px;
  margin: 0 10px -6px 0;
  border: 3px solid #18d26e;
  border-top-color: #eee;
  animation: animate-loading 1s linear infinite;
}

.Membership .php-email-form input,
.Membership .php-email-form textarea,
.Membership .php-email-form select {
  border-radius: 0;
  box-shadow: none;
  font-size: 14px;
  padding: 10px !important;
}

.Membership .php-email-form input:focus,
.Membership .php-email-form textarea:focus,
.Membership .php-email-form select:focus {
  border-color: #1977cc;
}

.Membership .php-email-form input,
.Membership .php-email-form select {
  height: 44px;
}

.Membership .php-email-form textarea {
  padding: 10px 12px;
}

.Membership .php-email-form button[type=submit] {
  background: #1977cc;
  border: 0;
  padding: 10px 35px;
  color: #fff;
  transition: 0.4s;
  border-radius: 50px;
}

.Membership .php-email-form button[type=submit]:hover {
  background: #1c84e3;
} */
/* button {
  --color: #0077ff;
  font-family: inherit;
  display: inline-block;
  width: 6em;
  padding: 1px;

  height: 2.6em;
  line-height: 2.5em;
  overflow: hidden;
  margin: 20px;
  font-size: 17px;
  z-index: 1;
  color: var(--color);
  border: 2px solid var(--color);
  border-radius: 6px;
  position: relative;
} */

button::before {
  position: absolute;
  content: "";
  background: var(--color);
  width: 150px;
  height: 200px;
  z-index: -1;
  border-radius: 50%;
}

button:hover {
  color: white;
}

button:before {
  top: 100%;
  left: 100%;
  transition: .3s all;
}

button:hover::before {
  top: -30px;
  left: -30px;
}


label {
  display: block;
  margin-bottom: 5px;
  color: #555;
}

input {
  width: 100%;
  padding: 8px;
  margin-bottom: 10px;
  box-sizing: border-box;
  border: 1px solid #e4e0e0;
  border-radius: 4px;
}

#success {
  display: block;
  background-color: #c1d9c2;
  color: white;
  padding: 5px;
  border-radius: 10px;
  text-align: center;
}

/* #form-container {
   width: 80%;
  margin: auto;
  background-color: #ffffff;
  padding: 20px; 
  border-radius: 10px;
  box-shadow: 5px 15px 10px rgba(0, 0, 0, 0.1);
 
} */

.form-step {
  /* display: none;
  animation: fadeIn 0.5s ease-in-out;
  margin-bottom: 20px; */
  display: flex;
    justify-content: space-between;
    align-items: center;
    width: 100%;
    padding: 5px 0;
    border-bottom: 1px solid #ccc;
}

@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateY(10px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

h2 {
  color: #333;
}
.butto {
  position: relative;
  transition: all 0.3s ease-in-out;
  box-shadow: 0px 10px 20px rgba(0, 0, 0, 0.2);
  padding-block: 0.5rem;
  padding-inline: 1.25rem;
  background-color: rgb(0 107 179);
  border-radius: 9999px;
  display: flex;
  align-items: center; 
  justify-content: center; 
  color: #ffff;
  gap: 10px;
  font-weight: bold;
  border: 3px solid #ffffff4d;
  outline: none;
  overflow: hidden;
  font-size: 15px;
}

.icon {
  width: 24px;
  height: 24px;
  transition: all 0.3s ease-in-out;
}

.butto:hover {
  transform: scale(1.05);
  border-color: #fff9;
}

.butto:hover .icon {
  transform: translate(4px);
}

.butto:hover::before {
  animation: shine 1.5s ease-out infinite;
}

.butto::before {
  content: "";
  position: absolute;
  width: 100px;
  height: 100%;
  background-image: linear-gradient(
    120deg,
    rgba(255, 255, 255, 0) 30%,
    rgba(255, 255, 255, 0.8),
    rgba(255, 255, 255, 0) 70%
  );
  top: 0;
  left: -100px;
  opacity: 0.6;
}

@keyframes shine {
  0% {
    left: -100px;
  }

  60% {
    left: 100%;
  }

  to {
    left: 100%;
  }
}


/*--------------------------------------------------------------
# Doctors
--------------------------------------------------------------*/
.staff {
  background: #fff;
}

.staff .member {
  position: relative;
  box-shadow: 0px 2px 15px rgba(44, 73, 100, 0.08);
  padding: 20px;
  border-radius: 10px;
}

.staff .member .pic {
  overflow: hidden;
  width: 180px;
  border-radius: 50%; 
  
}

.staff .member .pic img {
  transition: ease-in-out 0.3s;
}

.staff .member:hover img {
  transform: scale(1.1);
}

.staff .member .member-info {
  padding-left: 10px;
}

.staff .member h4 {
  font-weight: 700;
  margin-bottom: 5px;
  font-size: 20px;
  color: #2c4964;
}

.staff .member span {
  display: block;
  font-size: 15px;
  padding-bottom: 10px;
  position: relative;
  font-weight: 500;
}

.staff .member span::after {
  content: "";
  position: absolute;
  display: block;
  margin-left: 80px;
  width: 60%;
  height: 1px;
  background: #b2c8dd;
  bottom: 0;
  left: 0;
}

.staff .member p {
  margin: 10px 0 0 0;
  font-size: 14px;
}

.staff .member .social {
  margin-top: 12px;
  display: flex;
  align-items: center;
  justify-content: flex-start;
}

.staff .member .social a {
  transition: ease-in-out 0.3s;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 50px;
  width: 32px;
  height: 32px;
  background: #a0bcd5;
}

.staff .member .social a i {
  color: #fff;
  font-size: 16px;
  margin: 0 2px;
}

.staff .member .social a:hover {
  background: #1977cc;
}

.staff .member .social a+a {
  margin-left: 8px;
}
/*--------------------------------------------------------------
# Frequently Asked Questions
--------------------------------------------------------------*/
.faq .faq-list {
  padding: 0 100px;
  outline: none;

}

.faq .faq-list ul {
  padding: 0;
  list-style: none;
  
}

.faq .faq-list li+li {
  margin-top: 15px;
  border-radius: 15px;
  box-shadow: 5px 5px 12px rgba(137, 159, 180, 0.08);

}

.faq .faq-list li {
  padding: 20px;
  background: #ffffff;  border-radius: 4px;
  position: relative;
  border-radius: 15px;
  box-shadow: 5px 5px 12px rgba(137, 159, 180, 0.08);

}

.faq .faq-list a {
  /* display: block; */
  /* position: relative; */
  font-family: "Poppins", sans-serif;
  font-size: 20px;
  /* line-height: 2px; */
  font-weight: 500;
  padding: 0 30px;
  outline: none;
  cursor: pointer;
}

.faq .faq-list .icon-help {
  font-size: 30px;
  /* position: absolute; */
  right: 0;
  left: 0;
  color: #76b5ee;
}

.faq .faq-list .icon-show,
.faq .faq-list .icon-close {
  font-size: 24px;
  /* position: absolute;
  right: 0;
  top: 0; */
}

.faq .faq-list p {
  margin-bottom: 0;
  padding: 10px 0 0 0;
}

.faq .faq-list .icon-show {
  display: none;
}

.faq .faq-list a.collapsed {
  color: #343a40;

}



.faq .faq-list a.collapsed .icon-show {
  display: inline-block;
}

.faq .faq-list a.collapsed .icon-close {
  display: none;
}

@media (max-width: 1200px) {
  .faq .faq-list {
    padding: 0;
  }
}

/* events Section */
.events .testimonial-wrap {
  padding-left: 50px;
}

.events .events-carousel,
.events .events-slider {
  overflow: hidden;
}

.events .testimonial-item {
  box-sizing: content-box;
  padding: 30px 30px 30px 60px;
  margin: 30px 15px;
  min-height: 200px;
  box-shadow: 0px 2px 12px rgba(44, 73, 100, 0.08);
  position: relative;
  background: #fff;
}

.events .testimonial-item .testimonial-img {
  width: 90px;
  border-radius: 10px;
  border: 6px solid #fff;
  position: absolute;
  left: -45px;
}

.events .testimonial-item h3 {
  font-size: 18px;
  font-weight: bold;
  margin: 10px 0 5px 0;
  color: #111;
}

.events .testimonial-item h4 {
  font-size: 14px;
  color: #999;
  margin: 0;
}

.events .testimonial-item .quote-icon-left,
.events .testimonial-item .quote-icon-right {
  color: #badaf7;
  font-size: 26px;
}

.events .testimonial-item .quote-icon-left {
  display: inline-block;
  left: -5px;
  position: relative;
}

.events .testimonial-item .quote-icon-right {
  display: inline-block;
  right: -5px;
  position: relative;
  top: 10px;
}

.events .testimonial-item p {
  font-style: italic;
  margin: 15px auto 15px auto;
}

@media (max-width: 767px) {
  .events .testimonial-wrap {
    padding-left: 0;
  }

  .events .events-carousel,
  .events .events-slider {
    overflow: hidden;
  }

  .events .testimonial-item {
    padding: 30px;
    margin: 15px;
  }

  .events .testimonial-item .testimonial-img {
    position: static;
    left: auto;
  }
}

/* Swiper Styles */
.events .swiper-container {
  width: 100%;
}

.events .swiper-wrapper {
  display: flex;
}

.events .swiper-slide {
  flex: 0 0 auto;
  width: auto;
}

.events .swiper-pagination {
  margin-top: 20px;
  position: relative;
  display: flex;
  justify-content: center;
}

.events .swiper-pagination .swiper-pagination-bullet {
  width: 12px;
  height: 12px;
  background-color: #fff;
  opacity: 0.5;
  border: 1px solid #1977cc;
  margin: 0 5px; /* Add margin between bullets */
}

.events .swiper-pagination .swiper-pagination-bullet-active {
  background-color: #1977cc;
  opacity: 1;
}
/*--------------------------------------------------------------
# Contact
--------------------------------------------------------------*/
.contact .info {
  width: 100%;
  background: #fff;
}

.contact .info i {
  font-size: 20px;
  color: #1977cc;
  float: left;
  width: 44px;
  height: 44px;
  background: #d6e9fa;
  display: flex;
  justify-content: center;
  align-items: center;
  border-radius: 50px;
  transition: all 0.3s ease-in-out;
}

.contact .info h4 {
  padding: 0 0 0 60px;
  font-size: 22px;
  font-weight: 600;
  margin-bottom: 5px;
  color: #2c4964;
}

.contact .info p {
  padding: 0 0 0 60px;
  margin-bottom: 0;
  font-size: 14px;
  color: #4b7dab;
}

.contact .info .email,
.contact .info .phone {
  margin-top: 40px;
}

.contact .info .email:hover i,
.contact .info .address:hover i,
.contact .info .phone:hover i {
  background: #1977cc;
  color: #fff;
}

.contact .php-email-form {
  width: 100%;
  background: #fff;
}

.contact .php-email-form .form-group {
  padding-bottom: 8px;
}

.contact .php-email-form .error-message {
  display: none;
  color: #fff;
  background: #ed3c0d;
  text-align: left;
  padding: 15px;
  font-weight: 600;
}

.contact .php-email-form .error-message br+br {
  margin-top: 25px;
}

.contact .php-email-form .sent-message {
  display: none;
  color: #fff;
  background: #18d26e;
  text-align: center;
  padding: 15px;
  font-weight: 600;
}

.contact .php-email-form .loading {
  display: none;
  background: #fff;
  text-align: center;
  padding: 15px;
}

.contact .php-email-form .loading:before {
  content: "";
  display: inline-block;
  border-radius: 50%;
  width: 24px;
  height: 24px;
  margin: 0 10px -6px 0;
  border: 3px solid #18d26e;
  border-top-color: #eee;
  animation: animate-loading 1s linear infinite;
}

.contact .php-email-form input,
.contact .php-email-form textarea {
  border-radius: 0;
  box-shadow: none;
  font-size: 14px;
}

.contact .php-email-form input {
  height: 44px;
}

.contact .php-email-form textarea {
  padding: 10px 12px;
}

.contact .php-email-form button[type=submit] {
  background: #1977cc;
  border: 0;
  padding: 10px 35px;
  color: #fff;
  transition: 0.4s;
  border-radius: 50px;
}

.contact .php-email-form button[type=submit]:hover {
  background: #1c84e3;
}

@keyframes animate-loading {
  0% {
    transform: rotate(0deg);
  }

  100% {
    transform: rotate(360deg);
  }
}
/*--------------------------------------------------------------
# Footer
--------------------------------------------------------------*/
#footer {
  color: #444444;
  font-size: 14px;
  background: #f1f7fd;
  margin-bottom: -10px;
}

#footer .credits {
  padding-top: 5px;
  font-size: 13px;
  color: #444444;
  
}

#footer .social-links a {
  font-size: 18px;
  display: inline-block;
  background: #1977cc;
  color: #fff;
  line-height: 1;
  padding: 8px 0;
  margin-right: 4px;
  border-radius: 50%;
  text-align: center;
  width: 36px;
  height: 36px;
  transition: 0.3s;
}

#footer .social-links a:hover {
  background: #1c84e3;
  color: #fff;
  text-decoration: none;
}
/*--------------------------------------------------------------
# Back to top button
--------------------------------------------------------------*/
.back-to-top {
  position: fixed;
  /* visibility: hidden; */
  opacity: 1;
  right: 15px;
  bottom: 15px;
  z-index: 996;
  background: #1977cc;
  width: 40px;
  height: 40px;
  border-radius: 4px;
  transition: all 0.4s;
}

.back-to-top i {
  font-size: 28px;
  color: #fff;
  line-height: 0;
}

.back-to-top:hover {
  background: #298ce5;
  color: #fff;
}

.back-to-top.active {
  visibility: visible;
  opacity: 1;
}

.datepicker-dropdown {
  padding: 20px !important;
}

</style>