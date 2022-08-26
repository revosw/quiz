<script lang="ts">
  import Column from "./lib/flex/Column.svelte";
  import Row from "./lib/flex/Row.svelte";
  import Icon from "./lib/Icon.svelte";
  import Button from "./lib/surfaces/Button.svelte";
  import Image from "./lib/surfaces/Image.svelte";
  import Input from "./lib/surfaces/Input.svelte";
  import RoundButton from "./lib/surfaces/RoundButton.svelte";
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

  const abc = 2;
  function goBack() {}

  function deleteQuestion(question) {
    return function () {
      // delete question
    };
  }
</script>

<Column>
  <Row justify="start">
    <Button click={goBack}>Go back</Button>
  </Row>

  <Surface>
    <Column gap="loose">
      {#each questions as question, index}
        <Row>
          <Column>
            <!-- BUTTONS -->
            <RoundButton color="red" click={deleteQuestion(index)}>
              <Icon icon="trash" />
            </RoundButton>
            <RoundButton click={deleteQuestion(index)}>
              <Icon icon="up" />
            </RoundButton>
            <RoundButton click={deleteQuestion(index)}>
              <Icon icon="down" />
            </RoundButton>
          </Column>
          <div style="aspect-ratio: 1; height: 100%;">
            <Column>
              <Image src={question.img} />
              <Input value={question.img} placeholder="Image URL"  />
            </Column>
          </div>
          <!-- QUESTION + IMAGE URL -->
          <Input value={question.Q} type="multi" rows="6" placeholder="Question prompt" />
          <Column>
            <Row>
              <!-- ALTERNATIVE 1 + 2 -->
              <Input value={question.A1} type="multi" placeholder="Alternative 1" />
              <Input value={question.A2} type="multi" placeholder="Alternative 2" />
            </Row>
            <Row>
              <!-- ALTERNATIVE 3 + 4 -->
              <Input value={question.A3} type="multi" placeholder="Alternative 3" />
              <Input value={question.A4} type="multi" placeholder="Alternative 4" />
            </Row>
          </Column>
        </Row>
      {/each}
    </Column>
  </Surface>

  <Row justify="start">
    <Button click={goBack}>Add question</Button>
  </Row>
</Column>
