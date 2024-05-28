<script setup>


const props = defineProps({
  fieldName: String,
  iconName: String,
})

const inputText = ref(null);

const emit = defineEmits(['updateInput'])

onMounted(() => {
  inputText.value = "";
})

function useInput(str) {
  inputText.value = str;
  emit('updateInput', {text: inputText.value, fieldName: props.fieldName})
}

</script>

<template>

<div class="group">      
      <input type="text" required :name="props.fieldName"
      @input="useInput($event.target.value)">
      
      <span class="highlight"></span>
      <span class="bar"></span>
      <label>{{props.fieldName}}</label>
    </div>

</template>

<style scoped>

/* form starting stylings ------------------------------- */
.group 			  { 
  position:relative; 
  margin-bottom:45px;
  width: 80%;
}
input 				{
  font-size:18px;
  padding:10px 10px 10px 5px;
  display:block;
  width: 80%;
  background: none;
  border:none;
  border-bottom:1px solid var(--color-white);
}
input:focus 		{ outline:none; border-bottom: 0; }

/* LABEL ======================================= */
label 				 {
  color: var(--color-white); 
  font-size:18px;
  font-weight:normal;
  position:absolute;
  pointer-events:none;
  left:5px;
  top:10px;
  transition:0.3s ease-in all; 
  -moz-transition:0.3s ease-in all; 
  -webkit-transition:0.3s ease-in all;
}

/* active state */
input:focus ~ label, input:valid ~ label 		{
  top:-20px;
  font-size:16px;
  font-weight: bold;
  color: var(--color-red);
}

/* BOTTOM BARS ================================= */
.bar 	{ position:relative; display:block; width: 100%; }
.bar:before, .bar:after 	{
  content:'';
  height:2px; 
  width:0;
  bottom:1px; 
  position:absolute;
  background: var(--color-red); 
  transition:0.25s ease-in all; 
  -moz-transition:0.25s ease-in all; 
  -webkit-transition:0.25s ease-in all;
}
.bar:before {
  left:50%;
}
.bar:after {
  right:50%; 
}

/* active state */
input:focus ~ .bar:before, input:focus ~ .bar:after {
  width:50%;
}

/* HIGHLIGHTER ================================== */
.highlight {
  position:absolute;
  height:60%; 
  width:100px; 
  top:25%; 
  left:0;
  pointer-events:none;
  opacity:0.5;
}

/* active state */
input:focus ~ .highlight {
  -webkit-animation:inputHighlighter 0.3s ease;
  -moz-animation:inputHighlighter 0.3s ease;
  animation:inputHighlighter 0.3s ease;
}

/* ANIMATIONS ================ */
@-webkit-keyframes inputHighlighter {
	from { background: var(--color-dark); }
  to 	{ width:0; background:transparent; }
}
@-moz-keyframes inputHighlighter {
	from { background:var(--color-dark); }
  to 	{ width:0; background:transparent; }
}
@keyframes inputHighlighter {
	from { background:var(--color-dark); }
  to 	{ width:0; background:transparent; }
}

</style>