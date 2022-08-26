<script lang="ts">
  import Column from "./lib/flex/Column.svelte";
  import Row from "./lib/flex/Row.svelte";
import Icon from "./lib/Icon.svelte";
  import Button from "./lib/surfaces/Button.svelte";
  import Image from "./lib/surfaces/Image.svelte";
  import Surface from "./lib/surfaces/Surface.svelte";

  const questions = [
    {
      img: "https://upload.wikimedia.org/wikipedia/commons/thumb/e/e7/Everest_North_Face_toward_Base_Camp_Tibet_Luca_Galuzzi_2006.jpg/1920px-Everest_North_Face_toward_Base_Camp_Tibet_Luca_Galuzzi_2006.jpg",
      Q: "What is the tallest mountain in the world?",
      A1: "Mount Everest",
      A2: "Definitely not Mount Everest",
      A3: "K2",
      A4: "The alps",
    },
    {
      img: "https://www.rmg.co.uk/sites/default/files/styles/full_width_1440/public/OM4521603071020_Highly%20Commended_Crescent%20Moon%20During%20the%20Day%20%C2%A9%20Rafael%20Ruiz.jpg",
      Q: "Who walked on the moon?",
      A1: "Bugs Bunny",
      A2: "Shrek",
      A3: "Neil Armstrong",
      A4: "Noone has been there yet",
    },
    {
      img: "https://gardematicfountains.com/media/Water-fountains-set-fountain-pump-fountain-nozzle-led-light-whisper-4-lighting-main-by-gardematic-fountains-700x394.jpg",
      Q: "What is this?",
      A1: "A fountain",
      A2: "Water sprinkler",
      A3: "Fludd refill station",
      A4: "The thing that viciously foams when you put soap in it",
    },
  ];

  function onAnswerClick() {}
  const currentQuestion = questions[0];
</script>

<Column>
  <Surface padding="tight">
    <Column>
      <Image src={currentQuestion.img} />
      <span class="question">{currentQuestion.Q}</span>
    </Column>
  </Surface>

  <div class="answers">
    <Button click={onAnswerClick}>{currentQuestion.A1}</Button>
    <Button click={onAnswerClick}>{currentQuestion.A2}</Button>
    <Button click={onAnswerClick}>{currentQuestion.A3}</Button>
    <Button click={onAnswerClick}>{currentQuestion.A4}</Button>
  </div>
  <Row justify="space-between">
    <div class="info">
      <Icon icon="clock" />
      <span>18</span>
    </div>
    <div class="info">
      <span>4</span>
      <Icon icon="thinking" />
    </div>
  </Row>
</Column>


<style>
  .question {
    font-size: 2rem;
  }
  
  .answers {
    display: grid;
    grid-template-rows: 1fr 1fr;
    grid-template-columns: 1fr 1fr;
    gap: var(--tight);
  }

  .info {
    display: flex;
    gap: 8px;
    align-items: center;
  }
  .info > * {
    font-size: 1.5rem;
  }
</style>