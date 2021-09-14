<template>
  <svg
    :width="size"
    :height="size"
    viewBox="0 0 18 18"
    fill="none"
    xmlns="http://www.w3.org/2000/svg"
  >
    <g clip-path="url(#clip0)">
      <path
        d="M17.9955 18.0002V17.9994H18V11.3979C18 8.16841 17.3048 5.68066 13.5293 5.68066C11.7143 5.68066 10.4963 6.67666 9.99901 7.62091H9.94651V5.98216H6.36676V17.9994H10.0943V12.0489C10.0943 10.4822 10.3913 8.96716 12.3315 8.96716C14.2433 8.96716 14.2718 10.7552 14.2718 12.1494V18.0002H17.9955Z"
        :fill="variant === 'light' ? 'white': variant === 'dark' ? 'black':''"
      />
      <path
        d="M0.296997 5.98291H4.029V18.0002H0.296997V5.98291Z"
        :fill="variant === 'light' ? 'white': variant === 'dark' ? 'black':''"
      />
      <path
        d="M2.1615 0C0.96825 0 0 0.96825 0 2.1615C0 3.35475 0.96825 4.34325 2.1615 4.34325C3.35475 4.34325 4.323 3.35475 4.323 2.1615C4.32225 0.96825 3.354 0 2.1615 0V0Z"
        :fill="variant === 'light' ? 'white': variant === 'dark' ? 'black':''"
      />
    </g>
    <defs>
      <clipPath id="clip0">
        <rect width="18" height="18" fill="white" />
      </clipPath>
    </defs>
  </svg>
</template>

<script>
export default {
  name: 'LinkedndinIcon',
  props: {
    variant: {
      type: String,
      default: ''
    },
    size: {
      type: String,
      default: '13'
    }
  }
}
</script>
