<script setup>
import { ref } from 'vue'

defineProps([ 'userName', 'userMainInfo']
)


const count = ref(0)
</script>

<template>

  <div class="main-info">
    <div class="main-info__wrap-img">
      <img class="main-info__img" src='../assets/image.png' alt="user image">
    </div>
    <h1>{{ userName }}</h1>
    <p>{{ userMainInfo }}</p>
  </div>

  <ul class="social-main-info">
    <li class="social-main-info__item" v-for="info in infos" :key='info.id'>
      <div class="social-main-info__wrap-img">
        {{ info.socialInfoSvg}}
      </div>
      <div class="social-main-info__wrap-text">
        <p class="social-main-info__text">
          {{ info.socialInfo}}
        </p>
        {{ info.socialInfoLink }}
      </div>
    </li>
  </ul>

  <div class="socials"> 
    <p class="socials__title">Socials</p>
    <ul class="socials__list">
      <li class="social" v-for="social in socials" :key='social.id'>
        <div class="social__wrap-img">
          {{ social.socialSvg}}
        </div>
        <div class="social__wrap-info">
          <p class="social__name">
            {{ social.socialName}}
          </p>
          {{ social.socialLink }}
        </div>
      </li>
    </ul>
  </div>

  <div>
    <p>Languages</p>
    <ul>
      <li>
        <div>
          <svg width="32" height="28" viewBox="0 0 32 28" fill="none" xmlns="http://www.w3.org/2000/svg">
<g filter="url(#filter0_d_3_8730)">
<g clip-path="url(#clip0_3_8730)">
<rect x="8" y="6" width="16" height="12" fill="#E1E7FE"/>
<mask id="mask0_3_8730" style="mask-type:luminance" maskUnits="userSpaceOnUse" x="8" y="6" width="16" height="12">
<rect x="8" y="6" width="16" height="12" fill="white"/>
</mask>
<g mask="url(#mask0_3_8730)">
<path fill-rule="evenodd" clip-rule="evenodd" d="M8 6V18H24V6H8Z" fill="#F7FCFF"/>
<mask id="mask1_3_8730" style="mask-type:luminance" maskUnits="userSpaceOnUse" x="8" y="6" width="16" height="12">
<path fill-rule="evenodd" clip-rule="evenodd" d="M8 6V18H24V6H8Z" fill="white"/>
</mask>
<g mask="url(#mask1_3_8730)">
<path fill-rule="evenodd" clip-rule="evenodd" d="M8 6V10H24V6H8Z" fill="#FF8C1A"/>
<path fill-rule="evenodd" clip-rule="evenodd" d="M8 14V18H24V14H8Z" fill="#5EAA22"/>
<path fill-rule="evenodd" clip-rule="evenodd" d="M14 12C14 13.1046 14.8954 14 16 14C17.1046 14 18 13.1046 18 12C18 10.8954 17.1046 10 16 10C14.8954 10 14 10.8954 14 12ZM17.5 12C17.5 12.8284 16.8284 13.5 16 13.5C15.1716 13.5 14.5 12.8284 14.5 12C14.5 11.1716 15.1716 10.5 16 10.5C16.8284 10.5 17.5 11.1716 17.5 12Z" fill="#3D58DB"/>
<path fill-rule="evenodd" clip-rule="evenodd" d="M15.9972 12.4304L15.5803 13.9672L15.8244 12.3936L14.8184 13.628L15.6815 12.2898L14.2604 13.0083L15.5932 12.1368L14.0027 12.2152L15.5747 11.9611L14.0899 11.3858L15.6293 11.7931L14.5068 10.6636L15.7475 11.6618L15.1815 10.1734L15.9089 11.59L15.9972 10L16.0855 11.59L16.8129 10.1734L16.2469 11.6618L17.4876 10.6636L16.3651 11.7931L17.9046 11.3858L16.4197 11.9611L17.9918 12.2152L16.4013 12.1368L17.7341 13.0083L16.3129 12.2898L17.176 13.628L16.17 12.3936L16.4142 13.9672L15.9972 12.4304Z" fill="#3D58DB"/>
</g>
</g>
</g>
</g>
<defs>
<filter id="filter0_d_3_8730" x="0" y="0" width="32" height="28" filterUnits="userSpaceOnUse" color-interpolation-filters="sRGB">
<feFlood flood-opacity="0" result="BackgroundImageFix"/>
<feColorMatrix in="SourceAlpha" type="matrix" values="0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 127 0" result="hardAlpha"/>
<feOffset dy="2"/>
<feGaussianBlur stdDeviation="4"/>
<feColorMatrix type="matrix" values="0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0.06 0"/>
<feBlend mode="normal" in2="BackgroundImageFix" result="effect1_dropShadow_3_8730"/>
<feBlend mode="normal" in="SourceGraphic" in2="effect1_dropShadow_3_8730" result="shape"/>
</filter>
<clipPath id="clip0_3_8730">
<rect x="8" y="6" width="16" height="12" rx="2" fill="white"/>
</clipPath>
</defs>
          </svg>
        </div>
        <div>
          <p>Hindi</p>
          <p>Native</p>
        </div>
      </li>
      <li>
        <div>
          <svg width="16" height="12" viewBox="0 0 16 12" fill="none" xmlns="http://www.w3.org/2000/svg">
          <g clip-path="url(#clip0_3_8751)">
          <mask id="mask0_3_8751" style="mask-type:alpha" maskUnits="userSpaceOnUse" x="-2" y="-1" width="20" height="14">
          <path d="M15.5556 -1H0.444465C-0.537375 -1 -1.33331 -0.164265 -1.33331 0.866667V11.1333C-1.33331 12.1643 -0.537375 13 0.444465 13H15.5556C16.5374 13 17.3334 12.1643 17.3334 11.1333V0.866667C17.3334 -0.164265 16.5374 -1 15.5556 -1Z" fill="white"/>
          </mask>
          <g mask="url(#mask0_3_8751)">
          <path d="M15.5556 -1H0.444465C-0.537375 -1 -1.33331 -0.164265 -1.33331 0.866667V11.1333C-1.33331 12.1643 -0.537375 13 0.444465 13H15.5556C16.5374 13 17.3334 12.1643 17.3334 11.1333V0.866667C17.3334 -0.164265 16.5374 -1 15.5556 -1Z" fill="#22438B"/>
          <path fill-rule="evenodd" clip-rule="evenodd" d="M1.33336 -0.0666656L-0.467529 -0.042399L-0.444418 1.8L14.6507 12.0928L16.4614 12.0583L16.4276 10.2271L1.33336 -0.0666656Z" fill="white"/>
          <path fill-rule="evenodd" clip-rule="evenodd" d="M0.444492 -0.0666656L-0.444397 0.866668L15.5556 12.0667L16.4445 11.1333L0.444492 -0.0666656Z" fill="#C7152A"/>
          <path fill-rule="evenodd" clip-rule="evenodd" d="M14.6667 -0.0666656H16.4444V1.8C16.4444 1.8 5.99999 8.70293 1.34932 12.0928C1.29332 12.1339 -0.426675 12.0956 -0.426675 12.0956L-0.564453 10.3213L14.6667 -0.0666656Z" fill="white"/>
          <path fill-rule="evenodd" clip-rule="evenodd" d="M15.5938 -0.092804L16.4445 0.866663L0.444492 12.0667L-0.444397 11.1333L15.5938 -0.092804Z" fill="#C7152A"/>
          <path fill-rule="evenodd" clip-rule="evenodd" d="M5.77783 -0.0666656H10.2223V3.66667H16.4445V8.33333H10.2223V12.0667H5.77783V8.33333H-0.444397V3.66667H5.77783V-0.0666656Z" fill="white"/>
          <path fill-rule="evenodd" clip-rule="evenodd" d="M6.66671 -0.0666656H9.33338V4.6H16.4445V7.4H9.33338V12.0667H6.66671V7.4H-0.444397V4.6H6.66671V-0.0666656Z" fill="#C7152A"/>
          <path d="M15.5556 -0.53334H0.444479C-0.291901 -0.53334 -0.888855 0.0934609 -0.888855 0.86666V11.1333C-0.888855 11.9065 -0.291901 12.5333 0.444479 12.5333H15.5556C16.292 12.5333 16.8889 11.9065 16.8889 11.1333V0.86666C16.8889 0.0934609 16.292 -0.53334 15.5556 -0.53334Z" stroke="black" stroke-opacity="0.1"/>
          </g>
          </g>
          <defs>
          <clipPath id="clip0_3_8751">
          <rect width="18.6667" height="14" fill="white" transform="translate(-1.33331 -1)"/>
          </clipPath>
          </defs>
          </svg>
        </div>
        <div>
          <p>English</p>
          <p>Professional working</p>
        </div>
      </li>
      <li>
        <div>
          <svg width="32" height="28" viewBox="0 0 32 28" fill="none" xmlns="http://www.w3.org/2000/svg">
<g filter="url(#filter0_d_3_8766)">
<g clip-path="url(#clip0_3_8766)">
<rect x="8" y="6" width="16" height="12" fill="#E1E7FE"/>
<g clip-path="url(#clip1_3_8766)">
<mask id="mask0_3_8766" style="mask-type:alpha" maskUnits="userSpaceOnUse" x="8" y="6" width="16" height="12">
<path d="M22.4762 6H9.52381C8.68223 6 8 6.71634 8 7.6V16.4C8 17.2837 8.68223 18 9.52381 18H22.4762C23.3178 18 24 17.2837 24 16.4V7.6C24 6.71634 23.3178 6 22.4762 6Z" fill="white"/>
</mask>
<g mask="url(#mask0_3_8766)">
<path d="M22.4762 6H9.52381C8.68223 6 8 6.71634 8 7.6V16.4C8 17.2837 8.68223 18 9.52381 18H22.4762C23.3178 18 24 17.2837 24 16.4V7.6C24 6.71634 23.3178 6 22.4762 6Z" fill="#CD0B20"/>
<path fill-rule="evenodd" clip-rule="evenodd" d="M8 9.2H24V14.8H8V9.2Z" fill="#FFCB00"/>
<path fill-rule="evenodd" clip-rule="evenodd" d="M14.8571 10.9776V12.9936C14.8571 13.5536 14.3451 14.0016 13.7143 14.0016H12.1905C11.5611 14 11.0476 13.5496 11.0476 12.992V10.976C11.0476 10.5184 11.3889 10.136 11.8583 10.012C12 9.59599 12.4358 9.96879 12.9524 9.96879C13.472 9.96879 13.9048 9.59839 14.0465 10.0128C14.5143 10.14 14.8571 10.5232 14.8571 10.9776Z" fill="#C8B47C"/>
<path fill-rule="evenodd" clip-rule="evenodd" d="M14.8571 11.6H15.619V14H14.8571V11.6ZM10.2857 11.6H11.0476V14H10.2857V11.6Z" fill="#B5B5B5"/>
<path fill-rule="evenodd" clip-rule="evenodd" d="M14.8571 13.2H15.619V14H14.8571V13.2ZM10.2857 13.2H11.0476V14H10.2857V13.2Z" fill="#165C96"/>
<path fill-rule="evenodd" clip-rule="evenodd" d="M14.8571 10.8H15.619V11.6H14.8571V10.8ZM10.2857 10.8H11.0476V11.6H10.2857V10.8Z" fill="#A0790A"/>
<path fill-rule="evenodd" clip-rule="evenodd" d="M11.8095 10.8H12.5714V12H11.8095V10.8ZM13.3333 12.4H14.0952V13.6H13.3333V12.4Z" fill="#D20636"/>
<path fill-rule="evenodd" clip-rule="evenodd" d="M13.3333 10.8H14.0952V12H13.3333V10.8Z" fill="#A18793"/>
<path fill-rule="evenodd" clip-rule="evenodd" d="M11.8095 12.4H12.5714V13.6H11.8095V12.4Z" fill="#FFE100"/>
<path fill-rule="evenodd" clip-rule="evenodd" d="M12.5714 10.8L11.8095 10H14.0952L13.3333 10.8H12.5714Z" fill="#B6161A"/>
<path fill-rule="evenodd" clip-rule="evenodd" d="M12.5714 9.2H13.3333V10H12.5714V9.2Z" fill="#AC9300"/>
</g>
</g>
</g>
</g>
<defs>
<filter id="filter0_d_3_8766" x="0" y="0" width="32" height="28" filterUnits="userSpaceOnUse" color-interpolation-filters="sRGB">
<feFlood flood-opacity="0" result="BackgroundImageFix"/>
<feColorMatrix in="SourceAlpha" type="matrix" values="0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 127 0" result="hardAlpha"/>
<feOffset dy="2"/>
<feGaussianBlur stdDeviation="4"/>
<feColorMatrix type="matrix" values="0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0.06 0"/>
<feBlend mode="normal" in2="BackgroundImageFix" result="effect1_dropShadow_3_8766"/>
<feBlend mode="normal" in="SourceGraphic" in2="effect1_dropShadow_3_8766" result="shape"/>
</filter>
<clipPath id="clip0_3_8766">
<rect x="8" y="6" width="16" height="12" rx="2" fill="white"/>
</clipPath>
<clipPath id="clip1_3_8766">
<rect width="16" height="12" fill="white" transform="translate(8 6)"/>
</clipPath>
</defs>
          </svg>
        </div>
        <div>
          <p>Spanish</p>
          <p>Elementary</p>
        </div>
      </li>
    </ul>
  </div>

  <div>
    <p>Hobbies & Interests</p>
    <ul>
      <li>
        <div>
          <svg width="17" height="18" viewBox="0 0 17 18" fill="none" xmlns="http://www.w3.org/2000/svg">
          <circle cx="8.5" cy="9" r="6.375" stroke="black" stroke-width="1.41667" stroke-linecap="round" stroke-linejoin="round"/>
          <path d="M6.72919 11.1652V6.83477C6.72919 6.25863 7.38041 5.9235 7.84923 6.25838L10.8806 8.42362C11.2761 8.70611 11.2761 9.29391 10.8806 9.57641L7.84923 11.7416C7.38041 12.0765 6.72919 11.7414 6.72919 11.1652Z" stroke="black" stroke-width="1.41667" stroke-linecap="round" stroke-linejoin="round"/>
          </svg>
        </div>
        <div>
          <p>Gaming</p>
        </div>
      </li>
      <li>
        <div>
          <svg width="17" height="18" viewBox="0 0 17 18" fill="none" xmlns="http://www.w3.org/2000/svg">
          <circle cx="8.5" cy="9" r="6.375" stroke="black" stroke-width="1.41667" stroke-linecap="round" stroke-linejoin="round"/>
          <path d="M9.20832 2.65906C8.96181 2.86652 8.73972 3.11136 8.55077 3.39186C7.45796 5.01413 7.88716 7.21513 9.50943 8.30794C9.63748 8.3942 9.76914 8.47098 9.90358 8.53843C11.3333 9.25583 11.8792 8.28894 12.6533 8.81039C13.1554 9.14864 13.2882 9.8299 12.95 10.332C12.5955 10.8582 12.0416 11.125 12.1375 11.9869C12.1916 12.4733 12.4904 12.8925 12.8777 13.25" stroke="black" stroke-width="1.41667" stroke-linecap="round" stroke-linejoin="round"/>
          <path d="M2.83331 7.07336C3.59964 7.25986 4.30877 7.70221 4.8209 8.38088C5.36679 9.10429 5.59309 9.96927 5.52345 10.8065C5.48658 11.25 5.77577 11.6975 6.14789 11.9415C6.32769 12.0593 6.4906 12.2096 6.62753 12.3911C7.23388 13.1946 7.1129 14.3203 6.37498 14.9788" stroke="black" stroke-width="1.41667" stroke-linecap="round" stroke-linejoin="round"/>
          </svg>
        </div>
        <div>
          <p>Travelling</p>
        </div>
      </li>
      <li>
        <div>
          <svg width="17" height="18" viewBox="0 0 17 18" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path d="M2.83331 12.5417C2.83331 11.3681 3.78471 10.4167 4.95831 10.4167V10.4167C6.13192 10.4167 7.08331 11.3681 7.08331 12.5417V12.5417C7.08331 13.7153 6.13192 14.6667 4.95831 14.6667H3.11444C2.95918 14.6667 2.83331 14.5408 2.83331 14.3855V13.6042V12.5417V12.5417Z" stroke="black" stroke-width="1.41667" stroke-linecap="round" stroke-linejoin="round"/>
          <path d="M5.66669 10.2425L11.0428 4.26906C11.5858 3.66576 12.5236 3.6411 13.0975 4.21502L13.1913 4.30875L13.285 4.40248C13.8589 4.97641 13.8342 5.91424 13.231 6.45721L7.2575 11.8333" stroke="black" stroke-width="1.41667" stroke-linecap="round" stroke-linejoin="round"/>
          </svg>
        </div>
        <div>
          <p>Sketching/Graffitti</p>
        </div>
      </li>
      <li>
        <div>
          <svg width="17" height="18" viewBox="0 0 17 18" fill="none" xmlns="http://www.w3.org/2000/svg">
          <rect x="2.83331" y="3.33334" width="11.3333" height="11.3333" rx="2.125" stroke="black" stroke-width="1.41667" stroke-linecap="round"/>
          <path d="M2.83331 10.4167H6.37498" stroke="black" stroke-width="1.41667" stroke-linecap="round" stroke-linejoin="round"/>
          <path d="M10.625 10.4167H14.1667" stroke="black" stroke-width="1.41667" stroke-linecap="round" stroke-linejoin="round"/>
          <path d="M10.4968 10.4351C10.3473 10.8461 10.0745 11.2009 9.71581 11.4512C9.35711 11.7014 8.92994 11.8349 8.49258 11.8333C8.05523 11.8318 7.629 11.6954 7.27205 11.4426C6.91511 11.1899 6.64484 10.8332 6.49813 10.4212" stroke="black" stroke-width="1.41667" stroke-linecap="round" stroke-linejoin="round"/>
          </svg>
        </div>
        <div>
          <p>Blogging</p>
        </div>
      </li>
    </ul>
  </div>

  <div>
    <p>Personal Details</p>
    <li><span>Mother’s Name:</span> Pramila Devi</li>
    <li><span>Father’s Name:</span> Girish Chandra</li>
    <li><span>D.O.B. :</span> 10 - 04 - 2004</li>
  </div>

</template>


<script>
export default {
  data() {
    return {
      id: 'natali',
      infos: [
        {
          id: 'email',
          socialInfo: 'Email',
          socialInfoSvg:`<svg width="10" height="8" viewBox="0 0 10 8" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path d="M8.33331 7.33334H1.66665C1.20641 7.33334 0.833313 6.96024 0.833313 6.5V1.46376C0.852733 1.01773 1.2202 0.66625 1.66665 0.666672H8.33331C8.79355 0.666672 9.16665 1.03977 9.16665 1.50001V6.5C9.16665 6.96024 8.79355 7.33334 8.33331 7.33334ZM1.66665 2.27834V6.50001H8.33331V2.27834L4.99998 4.50001L1.66665 2.27834ZM1.99998 1.50001L4.99998 3.50001L7.99998 1.50001H1.99998Z" fill="#79819A"/>
          </svg>`,
          socialInfoLink:`<a href="mailto:anuragyadavmnp@gmail.com">anuragyadavmnp@gmail.com</a>`
        },
        {
          id: 'website',
          socialInfo: 'Website',
          socialInfoSvg: ` <svg width="8" height="9" viewBox="0 0 8 9" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path d="M2.52709 8.05626C1.68452 8.05626 0.924916 7.54872 0.602426 6.77031C0.279935 5.9919 0.458063 5.09588 1.05376 4.5L1.93793 3.61583L2.52709 4.205L1.64334 5.08875C1.32753 5.40456 1.2042 5.86486 1.31979 6.29626C1.43538 6.72766 1.77235 7.06463 2.20375 7.18022C2.63515 7.29581 3.09545 7.17248 3.41126 6.85667L4.29501 5.97292L4.88418 6.5625L4.00043 7.44625C3.61046 7.83814 3.07995 8.05778 2.52709 8.05626ZM2.82168 6.2675L2.23251 5.67833L5.17876 2.73208L5.76793 3.32125L2.82209 6.26708L2.82168 6.2675ZM6.06293 5.38375L5.47334 4.79458L6.35709 3.91083C6.6772 3.59597 6.80384 3.13361 6.68886 2.69958C6.57388 2.26554 6.23494 1.92652 5.80093 1.81144C5.36692 1.69635 4.90453 1.82288 4.58959 2.14292L3.70543 3.02667L3.11626 2.4375L4.00043 1.55333C4.81504 0.74582 6.12917 0.748698 6.94024 1.55977C7.75131 2.37085 7.75419 3.68497 6.94668 4.49958L6.06293 5.38333V5.38375Z" fill="#79819A"/>
        </svg>`,
        socialInfoLink: `<a href="https://anuragyadav365.github.io/portfolio.html">https://anuragyadav365.github.io/portfolio.html</a>`
        },
        {
          id: 'phone',
          socialInfo:'Phone',
          socialInfoSvg: `<svg width="8" height="8" viewBox="0 0 8 8" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path d="M6.91564 7.33332C3.3608 7.33837 0.662888 4.60812 0.666691 1.08438C0.666691 0.854258 0.853239 0.666664 1.08336 0.666664H2.18309C2.38958 0.666664 2.56499 0.818385 2.59531 1.02263C2.66798 1.51216 2.81051 1.98873 3.01856 2.43779L3.06137 2.53021C3.12091 2.65871 3.08055 2.81139 2.9653 2.89369C2.62473 3.13691 2.49457 3.62648 2.75989 4.00848C3.09284 4.48785 3.51254 4.90746 3.9918 5.24025C4.37378 5.5055 4.86327 5.37536 5.10648 5.03485C5.18884 4.91954 5.34161 4.87916 5.47019 4.93872L5.56218 4.98134C6.01126 5.18937 6.48787 5.3319 6.97745 5.40456C7.18171 5.43487 7.33335 5.61028 7.33335 5.81677V6.91666C7.33335 7.14677 7.14635 7.33332 6.91623 7.33332L6.91564 7.33332Z" fill="#79819A"/>
          </svg>`,
          socialInfoLink: `<a href="tel:(+91) 981 5533 309">(+91) 981 5533 309</a>`
        },
        {
          id: 'address',
          socialInfo: 'Address',
          socialInfoSvg: `<svg width="6" height="8" viewBox="0 0 6 8" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path d="M2.99998 7.75C2.4737 7.3011 1.98589 6.80897 1.54165 6.27875C0.87498 5.4825 0.0833134 4.29667 0.0833134 3.16667C0.0827225 1.98648 0.793416 0.922248 1.88376 0.470584C2.9741 0.0189204 4.22917 0.268852 5.06331 1.10375C5.61184 1.64984 5.91911 2.39266 5.91666 3.16667C5.91666 4.29667 5.12498 5.4825 4.45831 6.27875C4.01407 6.80897 3.52626 7.3011 2.99998 7.75ZM2.99998 1.91667C2.5534 1.91667 2.14074 2.15492 1.91745 2.54167C1.69416 2.92842 1.69416 3.40492 1.91745 3.79167C2.14074 4.17842 2.5534 4.41667 2.99998 4.41667C3.69034 4.41667 4.24998 3.85702 4.24998 3.16667C4.24998 2.47631 3.69034 1.91667 2.99998 1.91667Z" fill="#79819A"/>
          </svg>`,
          socialInfoLink: '<p>Hallomajra, Chandigarh, India</p>'
        }
      ],
      socials: [
        {
          id:'instagram',
          socialName: 'Instagram',
          socialSvg: `<svg width="10" height="11" viewBox="0 0 10 11" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path d="M3.33373 5.5002C3.33373 4.57972 4.07972 3.83333 5.0002 3.83333C5.92068 3.83333 6.66707 4.57972 6.66707 5.5002C6.66707 6.42068 5.92068 7.16707 5.0002 7.16707C4.07972 7.16707 3.33373 6.42068 3.33373 5.5002ZM2.43266 5.5002C2.43266 6.91826 3.58214 8.06774 5.0002 8.06774C6.41826 8.06774 7.56774 6.91826 7.56774 5.5002C7.56774 4.08214 6.41826 2.93266 5.0002 2.93266C3.58214 2.93266 2.4327 4.08206 2.4327 5.5002H2.43266ZM7.0694 2.83085C7.06936 2.94953 7.1045 3.06555 7.17039 3.16425C7.23628 3.26295 7.32997 3.33989 7.43959 3.38535C7.54921 3.43081 7.66985 3.44274 7.78625 3.41964C7.90265 3.39653 8.00959 3.33943 8.09354 3.25554C8.17749 3.17166 8.23468 3.06477 8.25788 2.94839C8.28107 2.832 8.26924 2.71135 8.22387 2.6017C8.1785 2.49204 8.10163 2.3983 8.00298 2.33233C7.90434 2.26635 7.78834 2.23112 7.66967 2.23107H7.66943C7.51035 2.23114 7.35782 2.29435 7.24531 2.40681C7.13281 2.51927 7.06954 2.67178 7.0694 2.83085ZM2.98012 9.57028C2.49262 9.54808 2.22765 9.46688 2.05156 9.39828C1.81811 9.30739 1.65155 9.19915 1.47642 9.02426C1.30129 8.84938 1.19289 8.68297 1.1024 8.44952C1.03376 8.27351 0.952558 8.00846 0.930397 7.52096C0.906156 6.9939 0.901316 6.83557 0.901316 5.50028C0.901316 4.16499 0.906556 4.0071 0.930397 3.4796C0.952598 2.9921 1.0344 2.72757 1.1024 2.55104C1.19329 2.31759 1.30153 2.15103 1.47642 1.9759C1.65131 1.80077 1.81771 1.69237 2.05156 1.60188C2.22757 1.53324 2.49262 1.45204 2.98012 1.42988C3.50718 1.40564 3.66551 1.4008 5.0002 1.4008C6.33489 1.4008 6.49338 1.40596 7.02088 1.42996C7.50838 1.45216 7.77291 1.53396 7.94944 1.60196C8.18289 1.69245 8.34945 1.80109 8.52458 1.97598C8.69971 2.15087 8.80771 2.31767 8.8986 2.55112C8.96724 2.72713 9.04844 2.99218 9.0706 3.47968C9.09484 4.00718 9.09968 4.16507 9.09968 5.50036C9.09968 6.83565 9.09484 6.99354 9.0706 7.52104C9.0484 8.00854 8.9668 8.27351 8.8986 8.4496C8.80771 8.68305 8.69947 8.84962 8.52458 9.02434C8.34969 9.19907 8.18289 9.30747 7.94944 9.39836C7.77343 9.467 7.50838 9.5482 7.02088 9.57036C6.49382 9.59461 6.33549 9.59945 5.0002 9.59945C3.66491 9.59945 3.50702 9.59461 2.98012 9.57036V9.57028ZM2.93872 0.530281C2.40642 0.554522 2.04268 0.638926 1.72503 0.762531C1.39626 0.890176 1.11756 1.06142 0.839274 1.33927C0.560982 1.61713 0.390176 1.89586 0.262531 2.22503C0.138926 2.54288 0.0545222 2.90642 0.0302812 3.43872C0.00564026 3.97186 0 4.14231 0 5.5002C0 6.8581 0.00564026 7.02854 0.0302812 7.56168C0.0545222 8.09403 0.138926 8.45752 0.262531 8.77537C0.390176 9.10415 0.561022 9.3834 0.839274 9.66113C1.11752 9.93886 1.39586 10.1099 1.72503 10.2379C2.04328 10.3615 2.40642 10.4459 2.93872 10.4701C3.47214 10.4944 3.64231 10.5004 5.0002 10.5004C6.35809 10.5004 6.52854 10.4948 7.06168 10.4701C7.59402 10.4459 7.95752 10.3615 8.27537 10.2379C8.60415 10.1099 8.88284 9.93898 9.16113 9.66113C9.43942 9.38328 9.60987 9.10415 9.73787 8.77537C9.86147 8.45752 9.94628 8.09399 9.97012 7.56168C9.99436 7.02814 10 6.8581 10 5.5002C10 4.14231 9.99436 3.97186 9.97012 3.43872C9.94588 2.90638 9.86147 2.54268 9.73787 2.22503C9.60987 1.89626 9.43898 1.61757 9.16113 1.33927C8.88328 1.06098 8.60414 0.890176 8.27577 0.762531C7.95752 0.638926 7.59398 0.554122 7.06208 0.530281C6.52886 0.50592 6.3585 0.5 5.0008 0.5C3.64311 0.5 3.47234 0.50564 2.93892 0.530281" fill="white"/>
          </svg>`,
          socialLink: `<a href="">@anuragyadav365</a>`
        },
        {
          id:'github',
          socialName: 'Github',
          socialSvg: `<svg width="11" height="11" viewBox="0 0 11 11" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M5.29918 0C2.37315 0 0 2.37271 0 5.29918C0 7.64054 1.51822 9.62685 3.6242 10.3277C3.88872 10.3767 3.97439 10.2124 3.97439 10.0729V9.08633C2.50033 9.40693 2.19342 8.46103 2.19342 8.46103C1.95231 7.84853 1.60477 7.68558 1.60477 7.68558C1.12387 7.35659 1.64142 7.36365 1.64142 7.36365C2.17355 7.40075 2.45352 7.90991 2.45352 7.90991C2.92603 8.7198 3.69309 8.48576 3.99558 8.35019C4.04283 8.00795 4.18017 7.7739 4.33208 7.64186C3.15522 7.50717 1.91786 7.05277 1.91786 5.02274C1.91786 4.44381 2.12497 3.97129 2.46368 3.60035C2.40892 3.46655 2.22742 2.92736 2.51535 2.19784C2.51535 2.19784 2.96048 2.05564 3.97306 2.741C4.39567 2.62354 4.84875 2.5648 5.29918 2.5626C5.74961 2.5648 6.20313 2.62354 6.62663 2.741C7.63833 2.05564 8.08258 2.19784 8.08258 2.19784C8.37094 2.9278 8.18944 3.46699 8.13469 3.60035C8.47472 3.97129 8.68006 4.44425 8.68006 5.02274C8.68006 7.05807 7.44049 7.50629 6.26054 7.63744C6.45043 7.80172 6.62398 8.12409 6.62398 8.61868V10.0729C6.62398 10.2137 6.70876 10.3793 6.9777 10.3272C9.08191 9.62552 10.5984 7.63965 10.5984 5.29918C10.5984 2.37271 8.22566 0 5.29918 0Z" fill="#24292E"/>
          </svg>`,
          socialLink: `<a href="">@anuragyadav365</a>`
        },
        {
          id:'twitter',
          socialName: 'Twitter',
          socialSvg: `<svg width="10" height="8" viewBox="0 0 10 8" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path d="M8.33126 1.28667C8.70477 1.06337 8.98425 0.711766 9.11751 0.2975C8.76653 0.505751 8.38252 0.652449 7.98209 0.73125C7.42692 0.14397 6.5473 0.00105286 5.83476 0.382357C5.12221 0.763661 4.75313 1.57479 4.93376 2.3625C3.49609 2.29032 2.15666 1.61122 1.24876 0.494167C0.77494 1.31143 1.01707 2.35616 1.80209 2.88167C1.51822 2.87254 1.24064 2.79568 0.992506 2.6575C0.992506 2.665 0.992506 2.6725 0.992506 2.68C0.992671 3.53131 1.59266 4.26462 2.42709 4.43333C2.16378 4.50497 1.88759 4.51552 1.61959 4.46417C1.85426 5.1922 2.52524 5.69095 3.29001 5.70583C2.6566 6.20297 1.87437 6.47257 1.06917 6.47125C0.926453 6.47146 0.783844 6.46325 0.64209 6.44667C1.45975 6.9721 2.41141 7.25098 3.38334 7.25C4.73553 7.25929 6.03502 6.72621 6.99114 5.77001C7.94727 4.81381 8.48024 3.51427 8.47084 2.16208C8.47084 2.08458 8.46903 2.0075 8.46542 1.93083C8.81561 1.67775 9.11784 1.36423 9.35792 1.005C9.03168 1.14961 8.68562 1.24455 8.33126 1.28667Z" fill="white"/>
          </svg>`,
          socialLink: `<a href="">@anuragyadav365</a>`
        },
        {
          id:'linkedin',
          socialName: 'Linkedin',
          socialSvg: ` <svg width="8" height="9" viewBox="0 0 8 9" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M4.41667 8.25H2.75V3.25H4.41667V4.08333C4.77193 3.63136 5.31068 3.36191 5.88542 3.34875C6.919 3.35449 7.753 4.19557 7.75001 5.22917V8.25H6.08333V5.4375C6.01668 4.97193 5.6174 4.62649 5.14708 4.6275C4.94137 4.634 4.74718 4.72407 4.60935 4.87693C4.47152 5.02978 4.40194 5.23221 4.41667 5.4375V8.25ZM1.91667 8.25H0.25V3.25H1.91667V8.25ZM1.08333 2.41667C0.623096 2.41667 0.25 2.04357 0.25 1.58333C0.25 1.1231 0.623096 0.75 1.08333 0.75C1.54357 0.75 1.91667 1.1231 1.91667 1.58333C1.91667 1.80435 1.82887 2.01631 1.67259 2.17259C1.51631 2.32887 1.30435 2.41667 1.08333 2.41667Z" fill="white"/>
          </svg>`,
          socialLink: `<a href="">@anuragyadav365</a>`,
        }
      ],
    };
  },
};

</script>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
