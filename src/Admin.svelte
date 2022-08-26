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
      img: "https://i.pcmag.com/imagery/roundups/01WOu4NbEnv3pJ54qp7j50k-16..v1647874749.jpg",
      Q: "Who are you going to call?",
      A1: "Ghost busters",
      A2: "Saul",
      A3: "Me",
      A4: "oh",
    },
    {
      img: "https://www.rmg.co.uk/sites/default/files/styles/full_width_1440/public/OM4521603071020_Highly%20Commended_Crescent%20Moon%20During%20the%20Day%20%C2%A9%20Rafael%20Ruiz.jpg",
      Q: "Who walked on the moon?",
      A1: "No one",
      A2: "James Bond",
      A3: "Terry Crews",
      A4: "Margaret Thatcher",
    },
    {
      img: "https://gardematicfountains.com/media/Water-fountains-set-fountain-pump-fountain-nozzle-led-light-whisper-4-lighting-main-by-gardematic-fountains-700x394.jpg",
      Q: "What is this?",
      A1: "A fountain",
      A2: "Bedrock",
      A3: "House",
      A4: "Ghost",
    },
  ];

  const abc = 2
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
            <RoundButton color="red" click={deleteQuestion(index)}
              ><Icon icon="trash" /></RoundButton
            >
            <RoundButton click={deleteQuestion(index)}
              ><Icon icon="up" /></RoundButton
            >
            <RoundButton click={deleteQuestion(index)}
              ><Icon icon="down" /></RoundButton
            >
          </Column>
          <div style="aspect-ratio: 1; height: 100%;">
            <Column>
              <Image src={question.img} />
              <Input placeholder="Image URL" />
            </Column>
          </div>
          <!-- QUESTION + IMAGE URL -->
          <Input type="multi" rows=6 placeholder="Question prompt" />
          <Column>
            <Row>
              <!-- ALTERNATIVE 1 + 2 -->
              <Input type='multi' placeholder="Alternative 1" />
              <Input type='multi' placeholder="Alternative 2" />
            </Row>
            <Row>
              <!-- ALTERNATIVE 3 + 4 -->
              <Input type='multi' placeholder="Alternative 3" />
              <Input type='multi' placeholder="Alternative 4" />
            </Row>
          </Column>
        </Row>
      {/each}
    </Column>
  </Surface>

  <Row justify="start">
    <Button click={goBack}>Go back</Button>
  </Row>
</Column>
