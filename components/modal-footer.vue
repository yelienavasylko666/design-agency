<template>
  <div v-bind:class="{ 'modal--show': show }" v-on:click="onClose($event)" class="modal">
    <div v-if="type === 'policy'" class="modal__window">
      <h1>Privacy Policy</h1>
      <div>
        We know that you care about your personal data and how it is used, and we want you to trust that welovedaily uses your personal data carefully. This Privacy Notice will help you understand what personal data we collect, why we collect it and what we do with it.

        Please take a moment to familiarise yourself with our privacy practices and let us know if you have any questions by sending us an email privacy@welovedaily.com.

        You have the right to object to certain uses of your personal data including the use of your personal data for direct marketing. See what are your rights and how you can exercise them here.
      </div>
      <div class="section">
        <h5>
          How We Use Your Information
        </h5>
        <ul>
          <li>To provide Designhill products/ services and resolve your queries.</li>
          <li>To share information, updates, offers about our products/ services and user subscription.</li>
          <li>To prepare reports, analyze data and pull out meaningful information to serve you better.</li>
          <li>To process financial transactions.</li>
          <li>To comply with legal and regulatory requirements and our policies.</li>
          <li>For the reasons apart from above mentioned, to market and promote the Services and to protect our interests and rights.</li>
        </ul>
      </div>
      <div class="section">
        <h5>With Whom We Share Your Personal Data</h5>
        <ul>
          <li>With our affiliates/ business partners/ service providers/ researchers who are bound by contractual obligations, to know the status of service(s) being used by user to improve their experience and help managing relationship.</li>
          <li>With Professionals i.e., accountants, auditors, lawyers, bankers and insurers to advise us on the services being offered to our users.</li>
          <li>With marketing and promotional companies to serve you with personalised ads/ promotions regarding our products and services.</li>
          <li>With Legal and Government departments related to compliance, audit, court orders, security, fraud, sale of assets, amalgamation/merger, acquisition, reorganisation, insolvency, etc. to comply with their regulations.</li>
        </ul>
      </div>
      <div class="section">
        <h5>How Long We Retain Your Personal Data</h5>
        <p>We retain your Personal Data as long as you keep your account with us and is reasonably needed. However, in some circumstances, we may keep it even after you close your account i.e., to comply with regulatory and legal obligations and to enforce our contracts/ agreements.</p>
      </div>
      <div class="section">
        <h5>Security of Personal Data</h5>
        <p>
          Designhill uses high standard safeguards to secure our users data to minimise the risk of loss/ unauthorised access of data. We respect your trust on Designhill, therefore we use highly encrypted systems/ applications to protect our databases.
          <br>We maintain stringent policies and procedures to deal with any Personal Data breach, however we cannot guarantee to absolute protection and security of Personal Data. We will inform you and the appropriate authorities in case of any breach of data security.
        </p>
      </div>
      <div class="section">
        <h5>Contact Us</h5>
        <p>
          Should you have any inquiries/ clarifications about this Privacy Policy, you may reach us by e-mail at web-support.helloy@gmail.com
          <br>
          Last updated on 27th February, 2020.
        </p>
      </div>
    </div>
    <div v-if="type === 'terms'" class="modal__window">
      <h5>1. Personal information we collect</h5>
      <div class="desc">
        In order to register on the Platform and identify yourself, we will request your email. To create your profile on the Platform you may include personal information such as your country or city of residence, a photograph, first and last names, education, work experience, and any other additional information you might want to share in your profile. The profile information helps you make the most out of our Services, like helping other professionals find you and finding business opportunities or projects you might be interested in. However, if you do not want this information to be published, you may leave the profile information fields blank or delete the information already provided.
        <br>
        When you visit or use our Services, We register data such as frequency of use, date and time Services were accessed, when you see or click a specific content, your content preferences. We use information when you log in, when you read our emails, and Internet protocol ("IP") addresses to identify you and register your use in the Platform.
        <br>
        We do not make decisions based on profiles, beyond personalization of advertisement and for the purpose of the legitimate prevention of Internet fraud.
        <br>
        We obtain information through other platforms, for example, when you register via Facebook or similar technologies. This might include personal texts or images available in an external website
      </div>
      <h5>2. Purpose</h5>
      <div class="desc">
        Manage your registration as Platform user, to identify you and give you access to Services available for registered Platform users.
        <br>
        Contacting you through email regarding updates or information related to features, products or services and updates, as long as they are needed or reasonable.
        <br>
        Respond to any request or inquiry you make through the customer service channels available at our Platform.
        <br>
        We also use your information to generate aggregated non-identifying data. For instance, generate statistics regarding our users, their jobs or areas of expertise, number of impressions or clicks in a specific project or visitor demographics.
      </div>
      <h5>3. Use of your credit card</h5>
      <div class="desc">
        You may have to provide a credit card to buy products and services from our website. We use third-party billing services and have no control over these services. We use our commercially reasonable efforts to make sure your credit card number is kept strictly confidential by using only third-party billing services that use industry-standard encryption technology to protect your credit card number from unauthorized use. However, you understand and agree that we are in no way responsible for any misuse of your credit card number.
        <br>
        If you are paying with PayPal, we will request the email associated to it. If you request an invoice, we will request your invoicing data, if needed.
        <br>
        We don’t save your details, but you will be able to modify or delete your credit cards or PayPal account at any time through the payment method in the purchase form or through the payment method setting in your profile.
        <br>
        For security reasons, the use of this feature might require changing of your password. Remember, the safety of the Platform also depends on the correct use and storage of confidential passwords.
      </div>
      <h5>4. Data retention period</h5>
      <div class="desc">
        We will retain your personal data for as long as we have a valid contractual relationship, and after that, for the period determined by any obligations arising from the treatment of the data or as established by law.
      </div>
      <h5>5. Changes</h5>
      <div class="desc">
        We will update this Privacy Policy occasionally and as required by legal, regulatory or operational modifications. We will notify such changes (including the effective date) as required by law.
      </div>
    </div>
    <div v-if="type === 'subscribe'" class="modal__window">
      <input v-bind:class="{ 'error' : !email.length }" v-model="email" type="email" placeholder="Enter your e-mail" class="text-center">
      <button @click.prevent.stop="onSubmit()" class="modal-open btn">
        Subscribe
      </button>
    </div>
  </div>
</template>
<script>
export default {
  name: 'ModalFooter',
  props: {
    show: Boolean,
    type: String
  },
  data: () => ({
    email: ''
  }),
  methods: {
    onClose (event) {
      if (event && event.target.className.includes('modal--show')) {
        this.$emit('close')
      }
    },
    onSubmit () {
      if (this.email.length) {
        this.$emit('close')
      }
    }
  }
}
</script>

<style scoped>
  .modal {
    position: fixed;
    width: 100vw;
    height: 100vh;
    background-color: rgba(78, 85, 91, 0.71);
  }
  .modal__window {
    position: fixed;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
    width: 900px;
    max-height: 80vh;
    overflow: auto;
    background-color: white;
    padding: 50px;
  }
  .modal--show {
    display: block;

  }
  .modal__window:last-child {
    display: flex;
    justify-content: space-between;
    flex-direction: column;
  }
  @media screen and (max-width: 1024px) {
    .modal__window {
      width: 650px;
    }
  }
  @media screen and (max-width: 768px) {
    .modal__window {
      width: 450px;
    }
  }
</style>
