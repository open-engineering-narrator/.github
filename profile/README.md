Open Engineering Narrator

Open Engineering Narrator is the implementation repository for the definitions provided by Open Engineering Narrators.

It provides the software that turns Open Engineering content into narrated experiences.

A Narrator can, for example, narrate an Open Engineering Tour, an Architecture Decision Record, or an Open Engineering Story.

From Narration Definition to Voice

Open Engineering Narrators define what a narrator is and what it can narrate.

Open Engineering Narrator provides the implementations that make those definitions executable.

Open Engineering Narrators
        │
        │ definitions
        ▼
Open Engineering Narrator
        │
        │ implementation
        ▼
   Narration Pipeline
        │
        ├── Open Engineering Tour
        ├── Architecture Decision Record
        ├── Open Engineering Story
        └── other narratable content
        │
        ▼
      Voice
        │
        ▼
      Audio

The implementation is deliberately separated from the definitions so that different narration technologies can be used without changing the Open Engineering Narrator model.

First Implementation: TTS-Story

The first narration tool integrated by this repository is TTS-Story.

TTS-Story provides a practical foundation for transforming structured text into spoken narratives, including support for multiple voices, speakers, chapters and sections.

Open Engineering Narrator uses TTS-Story as an implementation tool rather than making TTS-Story part of the Open Engineering Narrator definition.

This creates a clean boundary:

Open Engineering Narrator
        │
        ▼
 Narration Model
        │
        ▼
 TTS-Story Adapter
        │
        ▼
     TTS-Story
        │
        ▼
      Audio

Additional narration engines can be added later through the same implementation boundary.

Narrators as Open Engineering Components

A narrator should not be limited to converting a block of text into speech.

It can interpret the structure and semantics of an Open Engineering artifact and determine how that artifact should be narrated.

For example, an Open Engineering Tour can expose a sequence such as:

Enter Architecture
        ↓
Introduce Component
        ↓
Explain Component
        ↓
Navigate to Related Component
        ↓
Explain Relationship
        ↓
Continue Tour
        ↓
Conclude

The Narrator can turn these events into a coherent spoken experience.

This allows the same underlying content to be narrated in different ways:

* technical
* introductory
* documentary
* educational
* conversational
* multilingual
* character-based

The content remains the source of truth; the Narrator provides the voice.

Architecture

The implementation is intended to evolve towards a modular narration pipeline:

                 Open Engineering Content
                          │
                          ▼
                  Narration Adapter
                          │
                          ▼
                  Narration Model
                          │
                          ▼
                  Narrator Engine
                          │
             ┌────────────┼────────────┐
             ▼            ▼            ▼
         TTS-Story      Kokoro       Piper
             │            │            │
             └────────────┼────────────┘
                          ▼
                     Audio Output

The first implementation focuses on TTS-Story.

Other engines can be introduced without changing the Open Engineering Narrators definitions.

Relationship with Open Engineering Narrators

The two repositories have deliberately different responsibilities.

Repository	Responsibility
Open Engineering Narrators	Definitions of narrators
Open Engineering Narrator	Implementation of narrators

In other words:

Open Engineering Narrators defines the Narrator; Open Engineering Narrator makes the Narrator speak.

Future Direction

The implementation can grow beyond simple text-to-speech towards semantic narration.

Potential capabilities include:

* narration of Open Engineering Tours
* narration of Architecture Decision Records
* narration of Open Engineering Stories
* multiple speakers and characters
* voice profiles
* pronunciation dictionaries
* SSML generation
* scene-aware narration
* pauses and transitions
* multilingual narration
* generated introductions and conclusions
* incremental audio generation
* audio caching
* narration timelines
* synchronization between narration and visual experiences
* integration with Open Engineering Video
* integration with Open Engineering Presentations
* integration with Open Engineering Maps

This makes Narrators a bridge between structured engineering knowledge and human experience.

Open Engineering

Open Engineering is an ecosystem for describing, implementing, composing and experiencing engineering knowledge.

Open Engineering Narrator adds a voice to that ecosystem.

Open Engineering Narrators define the voice; Open Engineering Narrator gives it a body.
